# Diseño de Apps
#codigo
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp ({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      darkTheme: ThemeData.dark(),
      home: const HomePage(),
    );
  }
}

class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  @override
  Widget build(BuildContext context){
    return Scaffold(
      appBar: AppBar(title: const Text("Login Page",
          style: TextStyle(color: Colors.white),),
        centerTitle: true,
        backgroundColor: Colors.redAccent,
      ),
      body: const Column(
        children: [
          SizedBox(
            height: 50,
          ),
          Center(child: Text("Login Page", style: TextStyle(
            fontSize: 30,
            fontWeight: FontWeight.bold,
            color: Colors.redAccent
          ),)),
          SizedBox(
            height: 50,
          ),
          Padding(
            padding: EdgeInsets.all(8.0),
            child: TextField(
              decoration: InputDecoration(
                border: OutlineInputBorder(),
                hintText: "Enter your Email",
                labelText: "Email"),
            ),
          ),
          SizedBox(
          ),
          Padding(
            padding: const EdgeInsets.all(8.0),
            child: TextField(
              decoration: InputDecoration(
                  border: OutlineInputBorder(),
                  hintText: "Enter your password",
                  labelText: "Password"),
            ),
          ),

        ],
      ));
  }
}
#codigo2
main.dart 
import 'package:flutter/material.dart';

import 'home_screen.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      darkTheme: ThemeData.dark(),
      home:const HomePage() ,
    );
  }
}

class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {

  TextEditingController emailController = TextEditingController();
  TextEditingController passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text("Login Page",
              style: TextStyle(color: Colors.yellowAccent)),
          centerTitle: true,
          backgroundColor: Colors.redAccent,
        ),
        body: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            const SizedBox(
              height: 50,
            ),
            const Center(child: Text("Login Page", style: TextStyle(
                fontSize: 30,
                fontWeight: FontWeight.bold,
                color: Colors.redAccent),
            )),
            const SizedBox(
              height: 50,
            ),
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: TextField(
                controller: emailController,
                decoration: const InputDecoration(
                    border: OutlineInputBorder(
                      borderRadius: BorderRadius.all(Radius.circular(10)),
                    ),
                    hintText: "Enter your email",
                    labelText: "Email"),
              ),
            ),
            const SizedBox(
              height: 50,
            ),
            Padding(
              padding: const EdgeInsets.all(8.0),
              child: TextField(
                obscureText: true,
                controller: passwordController,
                decoration: const InputDecoration(
                    border: OutlineInputBorder(
                      borderRadius: BorderRadius.all(Radius.circular(10)),
                    ),
                    hintText: "Enter your password",
                    labelText: "Password"),
              ),
            ),
            const SizedBox(
              height: 50,
            ),
            Padding(
              padding: const EdgeInsets.only(left: 50.0, right: 50.0),
              child: ElevatedButton(
                  onPressed: () {
                    Navigator.push(
                      context,
                      MaterialPageRoute(builder: (context) =>
                          LandingPage(userEmail: emailController.text.trim(),
                          )),
                    );
                  },
                  child: const Text(
                    "Login",
                    style: TextStyle(fontSize: 20),
                  )),
            )
          ],
        ));
  }
}
#codigo3
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
      return MaterialApp(
        darkTheme: ThemeData.dark(),
        home: const HomePage(),
      );
  }
}

class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Basic components"),
        centerTitle: true,
      ),
      drawer: Drawer(
        child: ListView(
          padding: EdgeInsets.zero,
          children: [
            const DrawerHeader(
                decoration: BoxDecoration(color: Colors.redAccent),
                child: Text("Hola Usuario")),
            ListTile(
              leading: Icon(Icons.home),
              title: const Text("Home"),
              //trailing: Icon(Icons.home),
              //selected: ,
            ),
            ListTile(
              leading: Icon(Icons.work),
              title: const Text("Work"),
              //trailing: Icon(Icons.home),
              //selected: ,
            ),
            ListTile(
              leading: Icon(Icons.business_center),
              title: const Text("Bussiness"),
              //trailing: Icon(Icons.home),
              //selected: ,
            ),
          ],
        )),
      body: Column(),

    );
  }
}
#codigo formulario
