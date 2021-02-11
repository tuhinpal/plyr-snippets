        fetch("url")
        .then(response => response.text())
        .then(result => {
            var blob = new Blob([result], {
                type: "text/vtt"
            });
            const track = document.createElement('track');
            Object.assign(track, {
                label: 'language',
                default: true,
                src: window.URL.createObjectURL(blob)
            });
            video.appendChild(track);
        })
        .catch(error => console.log('error', error));`
