# test
testcode
<?php
  include('dbcon.php');
  //echo "im working <br>";
  if(isset($_GET['update'])){

    $id=$_GET['id'];
    $title=$_GET['title'];
    $category=$_GET['category'];

    $sql="UPDATE data SET title='$title', category='$category' WHERE id='$id'";
    $run=$conn->query($sql);

  }
  if(isset($_GET['show'])){
     click();

  }
  function click(){
    $sql1="SELECT * FROM data";
    $run1=$conn->query($sql1);
    $done=$run1->fetch_assoc();
    echo $done['title'];
  }


  ?>
  <!DOCTYPE html>
  <html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body>

    <form class="" action="sql.php" method="get">
      <input type="number" name='id' placeholder="userid">
      <input type="text" name='title' placeholder="title">
      <input type="text" name='category' placeholder='category'>
      <input type="submit" name="update">
    </form>

    <form  action="sql.php" method="get">
      <input type='submit' name='show' value="show">

    </form>
  </body>
  </html>
