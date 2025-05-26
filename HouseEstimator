const express = require('express');
const cors = require('cors');
const app = express();

app.use(cors());
app.use(express.json());

app.post('/estimate', (req, res) => {
  const { lotSize, levels, finish, design } = req.body;

  let costPerSqm;
  switch (finish) {
    case 'basic': costPerSqm = 25000; break;
    case 'standard': costPerSqm = 35000; break;
    case 'premium': costPerSqm = 50000; break;
    default: costPerSqm = 30000;
  }

  const floorArea = lotSize * levels;
  const estimatedCost = floorArea * costPerSqm;

  res.json({ estimatedCost });
});

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
