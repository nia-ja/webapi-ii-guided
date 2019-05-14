Async/Await vs Promises

Promise:
(req, res) => {
  db.find()
  .then(data => {
    res.json(data);
  })
  .catch(err => {
    res.status(500).json({ err });
  });
}

Bad form:
(req, res) => {
  const data = db.find();

  res.json(data);
}

Async / Await:
async (req, res) => {
  try {
    const data = await db.find();

    res.json(data);
  } catch (err) {
    res.status(500).json({ err });
  }

}