<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Campus Reuse Hub - Canvas README</title>
<style>
  body {
    background: #f0f4f8;
    display: flex;
    justify-content: center;
    padding: 20px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  canvas {
    background: white;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  }
</style>
</head>
<body>

<canvas id="readmeCanvas" width="800" height="1100"></canvas>

<script>
const canvas = document.getElementById('readmeCanvas');
const ctx = canvas.getContext('2d');

const padding = 40;
const lineHeight = 28;
const sectionGap = 50;
const maxWidth = canvas.width - padding * 2;

ctx.fillStyle = '#222';
ctx.font = 'bold 32px "Segoe UI"';
ctx.fillText('🏫 Campus Reuse Hub', padding, padding + 30);

ctx.font = 'italic 18px "Segoe UI"';
ctx.fillStyle = '#555';
ctx.fillText('A smart platform to help students reuse and exchange academic items efficiently', padding, padding + 70);

// Function to wrap text
function wrapText(context, text, x, y, maxWidth, lineHeight) {
  const words = text.split(' ');
  let line = '';
  for(let n = 0; n < words.length; n++) {
    let testLine = line + words[n] + ' ';
    let metrics = context.measureText(testLine);
    let testWidth = metrics.width;
    if(testWidth > maxWidth && n > 0) {
      context.fillText(line, x, y);
      line = words[n] + ' ';
      y += lineHeight;
    }
    else {
      line = testLine;
    }
  }
  context.fillText(line, x, y);
  return y + lineHeight;
}

let y = padding + 100;
ctx.fillStyle = '#000';
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('📌 Project Summary', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
const summaryText = 'Campus Reuse Hub is a frontend web project built to help students buy, sell, or donate used academic resources like textbooks, lab kits, calculators, and tools. It promotes a culture of reuse, sustainability, and student collaboration within college campuses.';
y = wrapText(ctx, summaryText, padding, y, maxWidth, lineHeight);

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('🚀 Features', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
const features = [
  '35+ preloaded academic items',
  'Each item has name, description, image, price, and contact info',
  'Fast-loading images for smooth browsing',
  'Fully responsive design using Bootstrap 5',
  'Built by students, for students'
];
features.forEach(feature => {
  ctx.fillText('• ' + feature, padding + 20, y);
  y += lineHeight;
});

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('🛠️ Tech Stack', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
const techStack = [
  'HTML5 — page structure',
  'CSS3 — styling and layout',
  'JavaScript — dynamic item rendering',
  'Bootstrap 5 — responsive design',
  'Google Fonts — clean typography'
];
techStack.forEach(item => {
  ctx.fillText('• ' + item, padding + 20, y);
  y += lineHeight;
});

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('📸 Sample Items', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
const items = [
  'Physics Textbook',
  'Scientific Calculator',
  'Arduino UNO',
  'Lab Kits and Tools',
  'DSP and Signal System Books',
  'Soldering Station',
  'Engineering Drawing Sets',
  '…and more!'
];
items.forEach(item => {
  ctx.fillText('• ' + item, padding + 20, y);
  y += lineHeight;
});

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('💡 Future Enhancements', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
const future = [
  'Login and item upload form',
  'Firebase backend integration',
  'Item filtering and search',
  'Transaction/request system'
];
future.forEach(f => {
  ctx.fillText('• ' + f, padding + 20, y);
  y += lineHeight;
});

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('👨‍💻 Developed By', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
const devBy = 'A passionate team of second-year ECE students from SNS College of Engineering, Tamil Nadu.\n“We believe in building tools that make student life easier, cheaper, and more sustainable.”';
y = wrapText(ctx, devBy, padding, y, maxWidth, lineHeight);

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('📬 Contact', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
ctx.fillText('Email: deepak@example.com', padding + 20, y);

y += sectionGap;
ctx.font = 'bold 24px "Segoe UI"';
ctx.fillText('📝 License', padding, y);
y += 35;

ctx.font = '16px "Segoe UI"';
ctx.fillText('MIT License — free to use and modify for academic and personal projects', padding + 20, y);

y += sectionGap + 10;
ctx.font = 'bold 28px "Segoe UI"';
ctx.fillStyle = '#007BFF';
ctx.fillText('🔁 Reduce Waste. Reuse Resources. Campus Reuse Hub.', padding, y);

</script>

</body>
</html>
