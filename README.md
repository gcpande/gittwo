I am trying to save user input details in firestore and then display in android Fragment.
HomeFragment and UsersFragment are menu items of navigation drawer.
In the RegisterFragment users are added and saved in firestore.
There is User1.java class which is instantiated when users' details are saved in firestore.
 User1 class object is added to hashMap and set to firestore document.
The user details are successfully saved in firestore.
Attempted to display this saved details in three fragment/in three ways:
1. CallbackFragment  ( to which we go from  drawer menu HomeFragment.)
2. MyDetailFragment  (to which we go from drawer menu UserFragment)
3. MyDetailFragment  (to which also we go from drawer menu UserFragment) 
In all cases DocumentSnapshot  has data. Following log is obtained:
 DocumentSnapshot data: {2131231070=1, one={address=AddressOne, mobile=1111111111, name=one, id=1, eMail=one@onemail.com}}
But fields are null i.e.
documentSnapshot.getString("name"); is null
and if we convert to object of User1 class by 
User1 user1 = document.toObject(User1.class);
then also object is null.
Rules set to : 
allow read, write: if true;
