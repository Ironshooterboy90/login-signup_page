# login-signup_page
 The login page allows users to enter their phone number and password, while the registration page includes fields for full name, email, phone number, password, and confirm password. The app is designed to be responsive, ensuring a consistent layout on all device sizes.  Author Frida
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}


class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'jiji Market',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // appBar: AppBar(
      //   title: const Text('jiji Market'),
      //   centerTitle: true,
      // ),
      body: Center(
        child: LayoutBuilder(
          builder: (context, constraints) {
            return Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                const Icon(
                  Icons.local_grocery_store,
                  color: Color.fromARGB(255, 142, 232, 6),
                  size: 100.0,
                  semanticLabel: 'jiji Market',
                ),
                const Center(
                  child: Row(
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                      Text(
                        'jiji',
                        textAlign: TextAlign.center,
                        style: TextStyle(
                            fontSize: 28,
                            fontWeight: FontWeight.bold,
                            color: Colors.lightGreen),
                      ),
                      Text(
                        'Market',
                        textAlign: TextAlign.center,
                        style: TextStyle(
                          fontSize: 28,
                          fontWeight: FontWeight.bold,
                        ),
                      ),
                    ],
                  ),
                ),
                const SizedBox(height: 50),
                const Text(
                  'Buy & Sell Online. Work From Home',
                  textAlign: TextAlign.center,
                  style: TextStyle(fontSize: 38, fontWeight: FontWeight.bold),
                ),
                const SizedBox(height: 30),
                SizedBox(
                  width: constraints.maxWidth * 0.6,
                  child: ElevatedButton(
                    onPressed: () {
                      Navigator.push(
                        context,
                        MaterialPageRoute(
                            builder: (context) => const LoginPage()),
                      );
                    },
                    style:
                        ElevatedButton.styleFrom(backgroundColor: Colors.blue),
                    child: const Text(
                      'Login',
                      style: TextStyle(
                          color: Color.fromARGB(255, 253, 199, 36),
                          fontSize: 18,
                          fontWeight: FontWeight.bold),
                    ),
                  ),
                ),
                SizedBox(height: constraints.maxHeight * 0.02),
                SizedBox(
                  width: constraints.maxWidth * 0.6,
                  child: ElevatedButton(
                    onPressed: () {
                      Navigator.push(
                        context,
                        MaterialPageRoute(
                            builder: (context) => const RegisterPage()),
                      );
                    },
                    style:
                        ElevatedButton.styleFrom(backgroundColor: Colors.green),
                    child: const Text(
                      'Register',
                      style: TextStyle(
                          color: Colors.white,
                          fontSize: 18,
                          fontWeight: FontWeight.bold),
                    ),
                  ),
                ),
              ],
            );
          },
        ),
      ),
    );
  }
}

class LoginPage extends StatefulWidget {
  const LoginPage({super.key});

  @override
  LoginPageState createState() => LoginPageState();
}

class LoginPageState extends State<LoginPage> {
  final TextEditingController _phoneController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Login'),
        centerTitle: true,
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Center(
          child: LayoutBuilder(
            builder: (context, constraints) {
              return SingleChildScrollView(
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    const Icon(
                      Icons.local_grocery_store,
                      color: Color.fromARGB(255, 142, 232, 6),
                      size: 100.0,
                      semanticLabel: 'jiji Market',
                    ),
                    const Center(
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        children: [
                          Text(
                            'jiji',
                            textAlign: TextAlign.center,
                            style: TextStyle(
                                fontSize: 28,
                                fontWeight: FontWeight.bold,
                                color: Colors.lightGreen),
                          ),
                          Text(
                            'Market',
                            textAlign: TextAlign.center,
                            style: TextStyle(
                              fontSize: 28,
                              fontWeight: FontWeight.bold,
                            ),
                          ),
                        ],
                      ),
                    ),
                    const SizedBox(height: 50),
                    const Text(
                      'Buy & Sell Online. Work From Home',
                      textAlign: TextAlign.center,
                      style:
                          TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: constraints.maxHeight * 0.02),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _phoneController,
                        decoration:
                            const InputDecoration(labelText: 'Phone Number'),
                        keyboardType: TextInputType.phone,
                      ),
                    ),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _passwordController,
                        decoration:
                            const InputDecoration(labelText: 'Password'),
                        obscureText: true,
                      ),
                    ),
                    SizedBox(height: constraints.maxHeight * 0.02),
                    SizedBox(
                      width: constraints.maxWidth * 0.6,
                      child: ElevatedButton(
                        onPressed: () {
                          // Handle login logic here
                        },
                        style: ElevatedButton.styleFrom(
                            backgroundColor: Colors.blue),
                        child: const Text(
                          'Login',
                          style: TextStyle(
                              color: Color.fromARGB(255, 253, 199, 36),
                              fontSize: 18,
                              fontWeight: FontWeight.bold),
                        ),
                      ),
                    ),
                    const SizedBox(height: 16,),
                    TextButton(
                      onPressed: () {
                        Navigator.pushReplacement(
                          context,
                          MaterialPageRoute(
                              builder: (context) => const RegisterPage()),
                        );
                      },
                      child: const Text(
                          "If you don't have an Account click here to Register."),
                    ),
                  ],
                ),
              );
            },
          ),
        ),
      ),
    );
  }
}

class RegisterPage extends StatefulWidget {
  const RegisterPage({super.key});

  @override
  RegisterPageState createState() => RegisterPageState();
}

class RegisterPageState extends State<RegisterPage> {
  final TextEditingController _fullNameController = TextEditingController();
  final TextEditingController _emailController = TextEditingController();
  final TextEditingController _phoneController = TextEditingController();
  final TextEditingController _passwordController = TextEditingController();
  final TextEditingController _confirmPasswordController =
      TextEditingController();

  void _register() {
    if (_passwordController.text != _confirmPasswordController.text) {
      ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Passwords do not match')),
      );
      return;
    }
    // Handle registration logic here
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Register'),
        centerTitle: true,
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Center(
          child: LayoutBuilder(
            builder: (context, constraints) {
              return SingleChildScrollView(
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    const Icon(
                      Icons.local_grocery_store,
                      color: Color.fromARGB(255, 142, 232, 6),
                      size: 100.0,
                      semanticLabel: 'jiji Market',
                    ),
                    const Center(
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        children: [
                          Text(
                            'jiji',
                            textAlign: TextAlign.center,
                            style: TextStyle(
                                fontSize: 28,
                                fontWeight: FontWeight.bold,
                                color: Colors.lightGreen),
                          ),
                          Text(
                            'Market',
                            textAlign: TextAlign.center,
                            style: TextStyle(
                              fontSize: 28,
                              fontWeight: FontWeight.bold,
                            ),
                          ),
                        ],
                      ),
                    ),
                    const SizedBox(height: 50),
                    const Text(
                      'Buy & Sell Online. Work From Home',
                      textAlign: TextAlign.center,
                      style:
                          TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                    ),
                    SizedBox(height: constraints.maxHeight * 0.02),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _fullNameController,
                        decoration:
                            const InputDecoration(labelText: 'Full Name'),
                      ),
                    ),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _emailController,
                        decoration: const InputDecoration(labelText: 'Email'),
                        keyboardType: TextInputType.emailAddress,
                      ),
                    ),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _phoneController,
                        decoration:
                            const InputDecoration(labelText: 'Phone Number'),
                        keyboardType: TextInputType.phone,
                      ),
                    ),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _passwordController,
                        decoration:
                            const InputDecoration(labelText: 'Password'),
                        obscureText: true,
                      ),
                    ),
                    SizedBox(
                      width: constraints.maxWidth * 0.8,
                      child: TextField(
                        controller: _confirmPasswordController,
                        decoration: const InputDecoration(
                            labelText: 'Confirm Password'),
                        obscureText: true,
                      ),
                    ),
                    SizedBox(height: constraints.maxHeight * 0.02),
                    SizedBox(
                      width: constraints.maxWidth * 0.6,
                      child: ElevatedButton(
                        onPressed: _register,
                        style: ElevatedButton.styleFrom(
                            backgroundColor: Colors.green),
                        child: const Text(
                          'Register',
                          style: TextStyle(
                              color: Colors.white,
                              fontSize: 18,
                              fontWeight: FontWeight.bold),
                        ),
                      ),
                    ),
                    const SizedBox(height: 16,),
                    TextButton(
                      onPressed: () {
                        Navigator.pushReplacement(
                          context,
                          MaterialPageRoute(
                              builder: (context) => const LoginPage()),
                        );
                      },
                      child: const Text(
                          "If you have an Account click here to Login."),
                    ),
                  ],
                ),
              );
            },
          ),
        ),
      ),
    );
  }
}
