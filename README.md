# learning-firebase

To add Firebase to your app, you'll need a Firebase project, the Firebase SDK, and a short snippet of initialization code that has a few details about your project.

## Firebase dashboard

### Home

#### Generate sample code to initialize your application.

* click the Home icon
* click __Add Firebase to your web app__

    <script src="https://www.gstatic.com/firebasejs/3.5.2/firebase.js"></script>
    <script>
      // Initialize Firebase
      // TODO: Replace with your project's customized code snippet
      var config = {
        apiKey: "<API_KEY>",
        authDomain: "<PROJECT_ID>.firebaseapp.com",
        databaseURL: "https://<DATABASE_NAME>.firebaseio.com",
        storageBucket: "<BUCKET>.appspot.com",
        messagingSenderId: "<SENDER_ID>",
      };
      firebase.initializeApp(config);
    </script>

### Database

#### Rules

On the Rules tab, update the default rules (for learning purposes only)

    {
      "rules": {
        ".read": "true",
        ".write": "true"
      }
    }

## Chrome

#### Console

    var database = firebase.database();
    var itemsRef = database.ref('items');

    // CREATE  
    itemsRef.push({first: 'Terry', last: 'Brown'});
    itemsRef.push({first: 'Geddy', last: 'Lee'});

    child = itemsRef.child("111-22-3333");
    child.set({first: 'Alex', last: 'Lifeson'});

    // READ
    itemsRef.on('child_added', function(snapshot) { console.log('ADD',snapshot.val()); });

    // UPDATE
    itemsRef.on('child_changed', function(snapshot) { console.log('CHANGE',snapshot.val()); });
    childRef = itemsRef.child("111-22-3333");
    childRef.update({first: 'Neil', last: 'Peart'});

    // DELETE
    itemsRef.on('child_removed', function(snapshot) { console.log('REMOVED',snapshot.val()); });
    childRef = itemsRef.child("111-22-3333");
    childRef.remove();


    // OTHER EVENTS
    itemsRef.on('child_moved', function(snapshot) { console.log('MOVED',snapshot.val()); });
