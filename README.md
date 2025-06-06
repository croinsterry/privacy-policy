class TermsAndConditionsPage extends StatelessWidget {
  const TermsAndConditionsPage({super.key});

  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final screenWidth = mediaQuery.size.width;
    final screenHeight = mediaQuery.size.height;
    final isLandscape = mediaQuery.orientation == Orientation.landscape;

    // Responsive font sizes and padding
    final titleFontSize = (screenWidth * (isLandscape ? 0.05 : 0.06)).clamp(18.0, 24.0);
    final bodyFontSize = (screenWidth * (isLandscape ? 0.035 : 0.04)).clamp(14.0, 18.0);
    final padding = (screenWidth * (isLandscape ? 0.06 : 0.04)).clamp(16.0, 24.0);

    return Scaffold(
      backgroundColor: Colors.white,
      appBar: PreferredSize(
        preferredSize: Size.fromHeight(screenHeight * 0.08),
        child: AppBar(
          title: Text(
            'Terms & Conditions',
            style: TextStyle(
              fontSize: titleFontSize,
              fontWeight: FontWeight.w700,
              color: Colors.white,
            ),
            semanticsLabel: 'Terms and Conditions',
            maxLines: 1,
            overflow: TextOverflow.ellipsis,
          ),
          backgroundColor: Colors.purple,
          elevation: 0,
          centerTitle: true,
          systemOverlayStyle: const SystemUiOverlayStyle(
            statusBarColor: Colors.purple,
            statusBarIconBrightness: Brightness.light,
            statusBarBrightness: Brightness.dark,
          ),
          leading: IconButton(
            icon: const Icon(Icons.arrow_back, color: Colors.white),
            onPressed: () => Navigator.of(context).pop(),
            tooltip: 'Back',
            splashRadius: 24,
          ),
          automaticallyImplyLeading: false,
        ),
      ),
      body: SafeArea(
        child: SingleChildScrollView(
          physics: const AlwaysScrollableScrollPhysics(),
          padding: EdgeInsets.all(padding),
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              SizedBox(height: screenHeight * 0.02),
              Text(
                'Terms and Conditions',
                style: TextStyle(
                  fontSize: titleFontSize,
                  fontWeight: FontWeight.w700,
                  color: Colors.black87,
                ),
                semanticsLabel: 'Terms and Conditions Header',
              ),
              SizedBox(height: screenHeight * 0.02),
              Text(
                'Welcome to HairCutEase ("we," "us," or "our"). These Terms and Conditions ("Terms") govern your use of the HairCutEase mobile application ("App") and related services, including appointment booking, virtual queue management, and payment processing. By accessing or using the App, you agree to be bound by these Terms and our Privacy Policy. If you do not agree, you must not use the App.',
                style: TextStyle(
                  fontSize: bodyFontSize,
                  color: Colors.black87,
                  height: 1.5,
                ),
                textAlign: TextAlign.justify,
                strutStyle: const StrutStyle(height: 1.5),
              ),
              SizedBox(height: screenHeight * 0.02),
              _buildSection(
                context: context,
                title: '1. Introduction',
                content: '''
HairCutEase is a platform that enables users to book salon and barbershop appointments, join virtual queues, and receive real-time updates. These Terms apply to all users, including customers and salon partners. We reserve the right to update these Terms at any time, and changes will be effective upon posting in the App or notification to users. Continued use of the App after changes constitutes acceptance of the updated Terms.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '2. User Accounts and Obligations',
                content: '''
To use certain features of the App, you must create an account and provide accurate, complete, and up-to-date information, including your name, email address, and payment details. You agree to:
- Use the App for lawful purposes and in compliance with these Terms.
- Maintain the confidentiality of your account credentials and notify us immediately at support@haircutease.com of any unauthorized use.
- Not share your account with others or allow others to access your account.
- Not engage in activities that disrupt the App, including attempting unauthorized access to our systems.
Failure to comply may result in suspension or termination of your account.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '3. Booking and Queue Management',
                content: '''
The App allows you to book appointments and join virtual queues with participating salons and barbershops. You agree to:
- Provide accurate booking information and arrive on time for appointments.
- Cancel or reschedule appointments promptly through the App to avoid no-show penalties, as determined by the salon’s policies.
- Acknowledge that virtual queue positions are estimates and may vary due to salon operations.
HairCutEase is not responsible for salon service quality, delays, or cancellations, but we will facilitate communication between you and the salon.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '4. Payments and Refunds',
                content: '''
Payments for services booked through the App are processed via secure third-party payment providers. You agree to:
- Provide valid payment information and authorize charges for booked services.
- Acknowledge that payment terms, including deposits or cancellation fees, are set by individual salons and displayed in the App.
- Contact the salon directly for refund requests, which are subject to the salon’s refund policy.
HairCutEase is not responsible for disputes arising from payments or refunds but may assist in facilitating resolutions.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '5. Intellectual Property',
                content: '''
All content in the App, including text, graphics, logos, images, and software, is the property of HairCutEase or its licensors and is protected by copyright, trademark, and other intellectual property laws. You may not reproduce, distribute, modify, or create derivative works of any App content without our prior written consent, except as permitted for personal, non-commercial use.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '6. Limitation of Liability',
                content: '''
To the fullest extent permitted by law, HairCutEase shall not be liable for any indirect, incidental, special, or consequential damages, including loss of profits, data, or goodwill, arising from:
- Your use of or inability to use the App.
- Errors, delays, or cancellations in bookings or queue management.
- Unauthorized access to your account or data.
- Actions or services provided by salons or third-party providers.
Our total liability for any claim shall not exceed the amount paid by you for the specific service giving rise to the claim.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '7. Termination',
                content: '''
We may suspend or terminate your access to the App without notice if you breach these Terms or for any other reason, including system maintenance or legal compliance. Upon termination, your right to use the App ceases immediately, and you must stop all use of the App. Any bookings or payments in progress will be handled per the salon’s policies.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '8. Governing Law and Dispute Resolution',
                content: '''
These Terms are governed by the laws of the State of Delaware, without regard to its conflict of law provisions. Any disputes arising from these Terms or your use of the App shall be resolved through negotiation or, if necessary, in the state or federal courts located in Wilmington, Delaware, which shall have exclusive jurisdiction.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              _buildSection(
                context: context,
                title: '9. Contact Us',
                content: '''
For questions, concerns, or feedback about these Terms or the App, please contact us at:
'Email: haircutease@gmail.com'
                          'Address: A 9 Rajdeep Apartment India Colony Road, Ahmedabad, Gujarat, India'
We aim to respond to all inquiries within 48 hours.
                ''',
                fontSize: bodyFontSize,
                screenHeight: screenHeight,
              ),
              SizedBox(height: screenHeight * 0.04),
              Center(
                child: Text(
                  'Last Updated: June 5, 2025',
                  style: TextStyle(
                    fontSize: bodyFontSize * 0.9,
                    color: Colors.grey,
                    fontStyle: FontStyle.italic,
                  ),
                  textAlign: TextAlign.center,
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }

  Widget _buildSection({
    required BuildContext context,
    required String title,
    required String content,
    required double fontSize,
    required double screenHeight,
  }) {
    return Padding(
      padding: EdgeInsets.only(bottom: screenHeight * 0.02),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text(
            title,
            style: TextStyle(
              fontSize: fontSize * 1.1,
              fontWeight: FontWeight.w600,
              color: Colors.black87,
            ),
            semanticsLabel: title,
          ),
          SizedBox(height: screenHeight * 0.01),
          Text(
            content.trim(),
            style: TextStyle(
              fontSize: fontSize,
              color: Colors.black87,
              height: 1.5,
            ),
            textAlign: TextAlign.justify,
            strutStyle: const StrutStyle(height: 1.5),
          ),
        ],
      ),
    );
  }
}
// Privacy Policy Page






class PrivacyPolicyPage extends StatelessWidget {
  const PrivacyPolicyPage({super.key});

  @override
  Widget build(BuildContext context) {
    // Get screen size for responsive design
    final screenSize = MediaQuery.of(context).size;
    final textScaleFactor = MediaQuery.of(context).textScaleFactor;

    return Scaffold(
      backgroundColor: Colors.white, // Set screen background color to white
      appBar: AppBar(
        title: const Text(
          'Privacy Policy',
          style: TextStyle(
            color: Colors.white,
            fontWeight: FontWeight.w600,
          ),
        ),
        backgroundColor: Colors.purple,
        elevation: 0,
        centerTitle: true,
        leading: IconButton(
          icon: const Icon(Icons.arrow_back, color: Colors.white),
          onPressed: () => Navigator.of(context).pop(),
          tooltip: 'Back',
        ),
      ),
      body: SafeArea(
        child: LayoutBuilder(
          builder: (context, constraints) {
            return SingleChildScrollView(
              padding: EdgeInsets.symmetric(
                horizontal: screenSize.width * 0.05, // 5% of screen width
                vertical: screenSize.height * 0.02, // 2% of screen height
              ),
              child: ConstrainedBox(
                constraints: BoxConstraints(
                  minHeight: constraints.maxHeight,
                ),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    Text(
                      'Privacy Policy',
                      style: TextStyle(
                        fontSize: 24 * textScaleFactor,
                        fontWeight: FontWeight.bold,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.03),
                    Text(
                      'HairCutEase ("we," "us," or "our") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your personal information when you use our mobile application ("App") or related services. By using HairCutEase, you agree to the practices described in this policy.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.03),
                    Text(
                      '1. Information We Collect',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'We collect the following types of information:\n'
                          '- **Personal Information**: Information you voluntarily provide, such as your name, email address, phone number, and payment details, when you register, book appointments, or make payments through the App.\n'
                          '- **Queue and Booking Data**: Details related to your appointment bookings, live queue participation, and preferences to manage your salon visits.\n'
                          '- **Usage Data**: Information about how you interact with the App, including features used, time spent, and navigation patterns.\n'
                          '- **Device Information**: Technical data such as device type, operating system, IP address, and unique device identifiers to optimize App performance.\n'
                          '- **Location Data**: With your consent, we may collect location information to provide real-time updates on queue status or nearby salons.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '2. How We Use Your Information',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'We use your information to:\n'
                          '- Facilitate appointment bookings and manage virtual queues.\n'
                          '- Process payments securely through our third-party payment processors.\n'
                          '- Send real-time updates and notifications about your bookings or queue status.\n'
                          '- Personalize your experience by suggesting salons or services based on your preferences.\n'
                          '- Improve the App’s functionality and user experience through analytics.\n'
                          '- Communicate with you, including responding to inquiries or sending promotional offers (with your consent).\n'
                          '- Ensure the security and integrity of our services.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '3. Sharing Your Information',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'We may share your information with:\n'
                          '- **Salon Partners**: To coordinate your bookings and queue management, we share necessary details (e.g., name, appointment time) with the relevant salon or barbershop.\n'
                          '- **Service Providers**: Third-party providers, such as payment processors or analytics services, who assist in operating the App. These providers are contractually obligated to protect your data.\n'
                          '- **Legal Compliance**: When required by law, regulation, or legal process, or to protect the safety, rights, or property of HairCutEase, our users, or the public.\n'
                          'We do not sell your personal information to third parties.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '4. Data Protection',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'We implement industry-standard technical and organizational measures to protect your personal information from unauthorized access, loss, or misuse. Payment transactions are processed using secure encryption. However, no system is entirely secure, and we cannot guarantee absolute security.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '5. Your Rights',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'Depending on your jurisdiction, you may have the right to:\n'
                          '- Access the personal information we hold about you.\n'
                          '- Request correction or deletion of your data.\n'
                          '- Opt out of data collection, processing, or marketing communications.\n'
                          '- Request a copy of your data in a portable format.\n'
                          'To exercise these rights, contact us at haircutease@gmail.com.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '6. Data Retention',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'We retain your personal information only for as long as necessary to provide our services, comply with legal obligations, or resolve disputes. Booking and payment data may be retained for accounting or compliance purposes as required by law.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '7. Third-Party Services',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'The App may integrate with third-party services, such as payment gateways or analytics tools. These services have their own privacy policies, and we encourage you to review them. HairCutEase is not responsible for the privacy practices of third-party services.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.02),
                    Text(
                      '8. Changes to This Privacy Policy',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'We may update this Privacy Policy to reflect changes in our practices or legal requirements. We will notify you of significant changes via the App or email. The updated policy will be effective upon posting.',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                      textAlign: TextAlign.justify,
                    ),
                    SizedBox(height: screenSize.height * 0.03),
                    Text(
                      'Contact Us',
                      style: TextStyle(
                        fontSize: 18 * textScaleFactor,
                        fontWeight: FontWeight.w600,
                        color: Colors.black87,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.01),
                    Text(
                      'If you have questions or concerns about this Privacy Policy or our data practices, please contact us at:\n'
                          'Email: haircutease@gmail.com\n'
                          'Address: A 9 Rajdeep Apartment India Colony Road, Ahmedabad, Gujarat, India',
                      style: TextStyle(
                        fontSize: 16 * textScaleFactor,
                        height: 1.5,
                      ),
                    ),
                    SizedBox(height: screenSize.height * 0.05),
                  ],
                ),
              ),
            );
          },
        ),
      ),
    );
  }
}

