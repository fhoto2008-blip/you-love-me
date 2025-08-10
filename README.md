<!DOCTYPE html><html lang="th">
<head>
    <meta charset="UTF-8">
    <title>ฉันรักเธอ</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #ffeef0;
            padding: 50px;
        }
        h1 {
            font-size: 2em;
            margin-bottom: 20px;
        }
        button {
            font-size: 1.2em;
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
            border-radius: 8px;
            border: none;
        }
        #yesBtn {
            background-color: #ff4d6d;
            color: white;
        }
        #noBtn {
            background-color: #ccc;
            color: black;
        }
        img {
            max-width: 200px;
            display: block;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h1 id="question">ฉันรักเธอ เธอรักฉันไหม?</h1>
    <div id="buttons">
        <button id="yesBtn">Yes</button>
        <button id="noBtn">No</button>
    </div>
    <div id="imageContainer"></div><script>
    const noImages = [
        'https://i.imgur.com/t3W4h5D.png', // แมวร้องไห้
        'https://i.imgur.com/7N8yP0R.png', // แมวท้อ
        'https://i.imgur.com/Yp0vX6V.png'  // แมวเบื่อ
    ];
    const heartImage = 'https://i.imgur.com/EZB4Q7R.png'; // หัวใจ

    let noClickCount = 0;

    document.getElementById('noBtn').addEventListener('click', () => {
        if (noClickCount < noImages.length) {
            document.getElementById('imageContainer').innerHTML = `<img src="${noImages[noClickCount]}" alt="แมว"/>`;
            noClickCount++;
            if (noClickCount === noImages.length) {
                document.getElementById('noBtn').remove();
            }
        }
    });

    document.getElementById('yesBtn').addEventListener('click', () => {
        document.getElementById('imageContainer').innerHTML = `<img src="${heartImage}" alt="หัวใจ"/>`;
        document.getElementById('buttons').remove();
        document.getElementById('question').textContent = '❤️';
    });
</script>

</body>
</html>
