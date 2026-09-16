db.students.insertOne({
  name: "Nishant",
  subjects1: ["Math", "Science", "English"],
  subjects2: ["Science", "English"]
})
db.students.aggregate([
  {
    $project: {
      name: 1,
      difference: {
        $setDifference: ["$subjects1", "$subjects2"]
      }
    }
  }
])
db.students.aggregate([
{
  $project: {
    result: {
      $setDifference: [
        ["Math", "Science", "English"],
        ["Science", "English"]
      ]
    }
  }
}
])
