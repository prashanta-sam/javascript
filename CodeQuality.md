# Code Quality

## Level 1

Re-write the below code to better code quality standards.

```
async function GET_daTA() {
  let r = await fetch("https://jsonplaceholder.typicode.com/todos/1");
  let DATA = await r.json();
  return DATA;
}
==================================================== Level 1 Answer========================================

    async function GET_daTA() 
    {
      try
        {
          let r = await fetch("https://jsonplaceholder.typicode.com/todos/1");
          if(!r.ok)
             throw new Error(`Failed to fetch Api`);

          let DATA = await r.json();
          return DATA;
        } 
        catch(er)
        {
          console.error('Error:', er);
        }
    }


==========================================================END===========================================

## Level 2

Re-write the below code to better code quality standards.
Hint: use modern ES6 syntax and reduce lines of code.

```
async function getUsers() {
  let doc = await Promise.all(getUser(), getProfile(), getPosts());

  let user = doc[0];
  let Profile = doc[1];
  let p = doc[2];

  const userProfile = {
    user: user,
    profile: Profile,
    posts: p
  };

  return userProfile;
}

==================================================== Level 2 Answer========================================
  async function getUsers() 
  {
      let [user,profile,posts] = await Promise.all(getUser(), getProfile(), getPosts());


      const userProfile = {
        user,
        profile,
        posts
      };

      return userProfile;
    }
==============================================END===========================================
## Level 3

Re-write the below code to better code quality standards.
Hint: use modern ES6 syntax and reduce lines of code.

```
async function getUsers(users) {
  const new_users = [];

  for (let i = 0; i < users.length; i = i + 1) {
    const newUser = user[i];
    newUser.id = i;

    new_users.push(newUser);
  }

  return new_users;
}


============================================== Level 3 Answer:===========================================
          async function getUsers(users) {
              let new_users=[]
              new_users = users.map((obj,i)=>({...obj,id:++i}))
              return new_users
          }
          let user=[{name:'ram'},{name:'sam'}]
          console.log("Original arrray : ", user)
          getUsers(user).then(r=> console.log("Updated array:" ,r))
==============================================END===========================================
