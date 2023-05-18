<template>
  <div>
    <video ref="videoElement" autoplay></video>
    <button @click="startRecording">Start Recording</button>
    <button @click="stopRecording">Stop Recording</button>
    <button @click="downloadRecording">Download Recording</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mediaStream: null,
      mediaRecorder: null,
      recordedChunks: []
    };
  },
  methods: {
    startRecording() {
      navigator.mediaDevices.getUserMedia({ video: true })
        .then((stream) => {
          this.mediaStream = stream;
          this.$refs.videoElement.srcObject = stream;
          this.mediaRecorder = new MediaRecorder(stream);
          this.mediaRecorder.ondataavailable = this.handleDataAvailable;
          this.recordedChunks = [];
          this.mediaRecorder.start();
        })
        .catch((error) => {
          console.log('Failed to access camera:', error);
        });
    },
    stopRecording() {
      if (this.mediaRecorder && this.mediaRecorder.state !== 'inactive') {
        this.mediaRecorder.stop();
        this.mediaStream.getTracks().forEach((track) => {
          track.stop();
        });
        this.$refs.videoElement.srcObject = null;
        this.mediaStream = null;
      }
    },
    handleDataAvailable(event) {
      if (event.data.size > 0) {
        this.recordedChunks.push(event.data);
      }
    },
    downloadRecording() {
      if (this.recordedChunks.length > 0) {
        const blob = new Blob(this.recordedChunks, { type: 'video/webm' });
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = 'recording.webm';
        a.click();
      }
    }
  }
}
</script>

<style scoped>
video {
  width: 100%;
  height: auto;
}
button {
  display: block;
  margin-top: 10px;
  padding: 8px 16px;
  background-color: teal;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}
</style>
