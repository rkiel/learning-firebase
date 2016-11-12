# learning-firebase

To add Firebase to your app, you'll need a Firebase project, the Firebase SDK, and a short snippet of initialization code that has a few details about your project.



Add Firebase to your web app

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

Update the default rules (for learning purposes only)

    {
      "rules": {
        ".read": "true",
        ".write": "true"
      }
    }

In Chrome console.

    var database = firebase.database();
    var ref = database.ref();
    ref.on('child_added', function(snapshot) { console.log(snapshot.val()); });
