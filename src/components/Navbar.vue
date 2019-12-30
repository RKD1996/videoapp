<template>
  <div class="navbar">
    <ul class="nav-menu">
      <li class="logo"><h1>Video Share</h1> </li>
      <li class="search"><input type="text" > <button>search</button> </li>
      <li class="nav-link">All Videos</li>
      <li class="nav-link">Login</li>
      <li class="nav-link">Sign-up</li>
    </ul>
  </div>
</template>
<script>

</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Pacifico&display=swap');
@import url('https://fonts.googleapis.com/css?family=Josefin+Sans&display=swap');
  .navbar{
    text-align: center;
    background: #000;
    border-bottom: 1px solid #ddd;
    border-radius: 0px 0px 20px 20px;
    border-left: 1px solid #ddd;
    border-right: 1px solid #ddd;
    box-shadow: 0 0 4px rgba(0,0,0,0.2);
    color: white;
    .nav-menu{
      margin: 0;
      padding: 0px;
      list-style: none;
      display: flex;
      align-items: center;
      .logo{
        flex-basis: 40%;
        padding: 15px;
        h1{
          font-family: 'Pacifico', cursive;
          margin: 0;
          padding: 0;
        }
      }
      .search {
        flex-basis: 20%;
        padding: 25px;
        display: flex;
        font-family: 'Josefin Sans', sans-serif;
        input{
          flex-basis: 80%;
          padding: 5px 10px;
          color: #222;
          border-radius: 25px 0px 0px 25px;
          outline: none;
        }
        button{
          font-family: 'Josefin Sans', sans-serif;
          flex-basis: 20%;
          border: 0;
          background: #005fff;
          color: white;
          padding: 0 15px;
          border-radius: 0px 25px 25px 0px;
          cursor: pointer;
          &:hover{
            box-shadow: 0 0 8px #005fff;
          }
        }
      }
      li{
        &.nav-link {
          font-family: 'Josefin Sans', sans-serif;
          flex-basis: 10%;
          padding: 30px;
          transition: .3s;
          cursor: pointer;
          &:hover{
            background: #111;
          }
        }
        &:last-child{
          &:hover{
            border-radius: 0px 0px 20px 0px;
          }
        }
      }
    }
  }
</style>
