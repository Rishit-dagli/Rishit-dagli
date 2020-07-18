class Generator {
    constructor() {
      this.days = document.getElementsByClassName('day');
      this.profileActivitySVG = document.getElementById('profile-activity');
      this.createImageButton = document.getElementById('create-image-btn');
      this.resetActivityButton = document.getElementById('reset-activity-btn');
      this.daysActivity = {};
      for (let i = 0; i < this.days.length; i++) {
        this.days[i].addEventListener('click', (event) => this.handleDayClick(event, i), false);
        // this.days[i].addEventListener('mouseover', (event) => this.handleDayClick(event, i), false);
      }
      this.createImageButton.addEventListener('click', this.createImage, false);
      this.resetActivityButton.addEventListener('click', this.resetActivity, false);
    }
  
    handleDayClick = (event, index) => {
      this.daysActivity[index] = this.daysActivity[index] ? this.daysActivity[index] + 1 : 1;
      switch(this.daysActivity[index]) {
        case 1:
          event.target.setAttribute('fill', '#c6e48b');
          break;
        case 2:
          event.target.setAttribute('fill', '#7bc96f');
          break;
        case 3:
          event.target.setAttribute('fill', '#239a3b');
          break;
        case 4:
          event.target.setAttribute('fill', '#196127');
          break;
      }
    }
  
    createImage = () => {
      const serialized = new XMLSerializer().serializeToString(this.profileActivitySVG);
      const encodedData = window.btoa(serialized);
      this.createImageTag(encodedData);
    }
  
    resetActivity = () => {
      for (let i = 0; i < this.days.length; i++) {
        this.days[i].setAttribute('fill', '#ebedf0');
      }
    }
  
    createImageTag = (src) => {
      const image = new Image();
      image.src = `data:image/svg+xml;base64,${src}`;
      image.onload = function() {
        const canvas = document.createElement('canvas');
        const downloadLink = document.createElement('a');
        const context = canvas.getContext('2d');
  
        canvas.width = image.width;
        canvas.height = image.height;
        context.drawImage(image, 0, 0);
  
        downloadLink.download = 'result.png';
        downloadLink.href = canvas.toDataURL('image/png');
        downloadLink.click();
      }
    }
  }
  
  new Generator();
