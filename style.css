document.getElementById('image-form').addEventListener('submit', function(event) {
    event.preventDefault();

    const fileInput = document.getElementById('fileInput');
    const sizeSelect = document.getElementById('sizeSelect');
    const file = fileInput.files[0];
    const size = sizeSelect.value.split('x'); // Get width and height from selected size
    
    if (!file) {
        alert("Please upload an image!");
        return;
    }

    const reader = new FileReader();
    reader.onload = function(e) {
        const img = new Image();
        img.src = e.target.result;

        img.onload = function() {
            const canvas = document.createElement('canvas');
            const ctx = canvas.getContext('2d');

            // Set canvas size based on selected size
            canvas.width = parseInt(size[0]);
            canvas.height = parseInt(size[1]);

            // Draw image onto canvas and resize it
            ctx.drawImage(img, 0, 0, canvas.width, canvas.height);

            // Create the image from the canvas
            const convertedImageURL = canvas.toDataURL('image/png');

            // Display the converted image
            const resultImage = document.getElementById('convertedImage');
            resultImage.src = convertedImageURL;
            resultImage.style.display = 'block';

            // Create a download link for the image
            const downloadLink = document.getElementById('downloadLink');
            downloadLink.href = convertedImageURL;
            downloadLink.style.display = 'inline';
        };
    };

    reader.readAsDataURL(file);
});
