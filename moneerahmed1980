<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تعديل ألوان الصور</title>
    <style>
        body { text-align: center; font-family: Arial, sans-serif; background-color: #222; color: white; }
        .editor-container { margin: 20px auto; max-width: 800px; }
        canvas { max-width: 100%; margin-top: 20px; border-radius: 10px; }
        input, button { margin-top: 10px; padding: 10px; }
    </style>
</head>
<body>
    <h1>محرر الألوان السينمائي</h1>
    <input type="file" id="imageInput" accept="image/*">
    <input type="range" id="skyColor" min="0" max="100" value="50">
    <input type="range" id="lightIntensity" min="0" max="100" value="50">
    <button onclick="applyFilters()">تطبيق التعديلات</button>
    <canvas id="canvas"></canvas>

    <script>
        let canvas = document.getElementById("canvas");
        let ctx = canvas.getContext("2d");
        let img = new Image();

        document.getElementById("imageInput").addEventListener("change", function(event) {
            let file = event.target.files[0];
            if (file) {
                let reader = new FileReader();
                reader.onload = function(e) {
                    img.src = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        });

        img.onload = function() {
            canvas.width = img.width / 2;
            canvas.height = img.height / 2;
            ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
        };

        function applyFilters() {
            let skyAdjust = document.getElementById("skyColor").value;
            let lightAdjust = document.getElementById("lightIntensity").value;
            ctx.filter = `brightness(${1 + lightAdjust / 100}) contrast(${1 + skyAdjust / 100})`;
            ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
        }
    </script>
</body>
</html>
https://github.com/moneerahmed1980/image-editor.git
