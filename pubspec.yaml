import 'package:flutter/material.dart';

void main() {
  runApp(const MohamedKoraApp());
}

const Color bg = Color(0xFF080B09);
const Color panel = Color(0xFF151B17);
const Color green = Color(0xFF39F56A);
const Color muted = Color(0xFF9BA69E);

class MohamedKoraApp extends StatelessWidget {
  const MohamedKoraApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'mohamed kora',
      theme: ThemeData(
        brightness: Brightness.dark,
        scaffoldBackgroundColor: bg,
        colorScheme: ColorScheme.fromSeed(
          seedColor: green,
          brightness: Brightness.dark,
        ),
        useMaterial3: true,
      ),
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
  int selectedIndex = 0;

  final List<Widget> pages = const [
    HomeTab(),
    MatchesTab(),
    NewsTab(),
    LeagueTab(),
  ];

  final List<String> titles = [
    'الرئيسية',
    'المباريات',
    'الأخبار',
    'الدوريات',
  ];

  @override
  Widget build(BuildContext context) {
    return Directionality(
      textDirection: TextDirection.rtl,
      child: Scaffold(
        appBar: AppBar(
          backgroundColor: bg,
          title: Row(
            children: [
              const Icon(Icons.sports_soccer, color: green, size: 30),
              const SizedBox(width: 8),
              const Text(
                'mohamed ',
                style: TextStyle(
                  color: Colors.white,
                  fontWeight: FontWeight.bold,
                ),
              ),
              const Text(
                'kora',
                style: TextStyle(
                  color: green,
                  fontWeight: FontWeight.bold,
                ),
              ),
            ],
          ),
          actions: [
            IconButton(
              onPressed: () {
                ScaffoldMessenger.of(context).showSnackBar(
                  const SnackBar(
                    content: Text('سيتم إضافة التنبيهات لاحقًا'),
                  ),
                );
              },
              icon: const Icon(Icons.notifications_none),
            ),
          ],
        ),
        body: Column(
          children: [
            Container(
              width: double.infinity,
              padding: const EdgeInsets.symmetric(
                horizontal: 16,
                vertical: 10,
              ),
              color: panel,
              child: Text(
                titles[selectedIndex],
                style: const TextStyle(
                  fontSize: 21,
                  fontWeight: FontWeight.bold,
                ),
              ),
            ),
            Expanded(child: pages[selectedIndex]),
          ],
        ),
        bottomNavigationBar: NavigationBar(
          backgroundColor: panel,
          indicatorColor: green.withAlpha(46),
          selectedIndex: selectedIndex,
          onDestinationSelected: (index) {
            setState(() => selectedIndex = index);
          },
          destinations: const [
            NavigationDestination(
              icon: Icon(Icons.home_outlined),
              selectedIcon: Icon(Icons.home, color: green),
              label: 'الرئيسية',
            ),
            NavigationDestination(
              icon: Icon(Icons.sports_soccer_outlined),
              selectedIcon: Icon(Icons.sports_soccer, color: green),
              label: 'المباريات',
            ),
            NavigationDestination(
              icon: Icon(Icons.article_outlined),
              selectedIcon: Icon(Icons.article, color: green),
              label: 'الأخبار',
            ),
            NavigationDestination(
              icon: Icon(Icons.emoji_events_outlined),
              selectedIcon: Icon(Icons.emoji_events, color: green),
              label: 'الدوريات',
            ),
          ],
        ),
      ),
    );
  }
}

class HomeTab extends StatelessWidget {
  const HomeTab({super.key});

  @override
  Widget build(BuildContext context) {
    return ListView(
      padding: const EdgeInsets.all(16),
      children: [
        Container(
          padding: const EdgeInsets.all(20),
          decoration: BoxDecoration(
            borderRadius: BorderRadius.circular(18),
            gradient: const LinearGradient(
              colors: [Color(0xFF173D24), Color(0xFF101712)],
            ),
          ),
          child: const Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              Icon(Icons.sports_soccer, color: green, size: 38),
              SizedBox(height: 12),
              Text(
                'عالم كرة القدم بين إيديك',
                style: TextStyle(
                  fontSize: 22,
                  fontWeight: FontWeight.bold,
                ),
              ),
              SizedBox(height: 6),
              Text(
                'تابع المباريات والأخبار وترتيب الدوريات',
                style: TextStyle(color: muted),
              ),
            ],
          ),
        ),
        const SizedBox(height: 24),
        const SectionTitle(title: 'مباريات تجريبية'),
        const SizedBox(height: 10),
        const MatchCard(
          home: 'الأهلي',
          away: 'الزمالك',
          score: '0 - 0',
          status: 'بيانات تجريبية',
          homeIcon: Icons.shield,
          awayIcon: Icons.shield_outlined,
        ),
        const MatchCard(
          home: 'ريال مدريد',
          away: 'برشلونة',
          score: '0 - 0',
          status: 'بيانات تجريبية',
          homeIcon: Icons.sports_soccer,
          awayIcon: Icons.sports_soccer,
        ),
        const SizedBox(height: 24),
        const SectionTitle(title: 'أحدث الأخبار'),
        const SizedBox(height: 10),
        const NewsCard(
          title: 'أخبار كرة القدم',
          description: 'سيتم عرض الأخبار الحقيقية بعد ربط مصدر بيانات.',
          icon: Icons.newspaper,
        ),
        const SizedBox(height: 12),
        const NewsCard(
          title: 'سوق الانتقالات',
          description: 'تابع أخبار انتقالات اللاعبين والأندية.',
          icon: Icons.swap_horiz,
        ),
        const SizedBox(height: 16),
        const Text(
          'ملاحظة: كل النتائج والأخبار الحالية تجريبية.',
          style: TextStyle(color: muted, fontSize: 12),
        ),
      ],
    );
  }
}

class MatchesTab extends StatelessWidget {
  const MatchesTab({super.key});

  @override
  Widget build(BuildContext context) {
    return ListView(
      padding: const EdgeInsets.all(16),
      children: const [
        SectionTitle(title: 'المباريات'),
        SizedBox(height: 12),
        MatchCard(
          home: 'الأهلي',
          away: 'الزمالك',
          score: '0 - 0',
          status: 'موعد تجريبي',
          homeIcon: Icons.shield,
          awayIcon: Icons.shield_outlined,
        ),
        MatchCard(
          home: 'ليفربول',
          away: 'مانشستر سيتي',
          score: '0 - 0',
          status: 'موعد تجريبي',
          homeIcon: Icons.sports_soccer,
          awayIcon: Icons.sports_soccer,
        ),
        MatchCard(
          home: 'ريال مدريد',
          away: 'برشلونة',
          score: '0 - 0',
          status: 'موعد تجريبي',
          homeIcon: Icons.sports_soccer,
          awayIcon: Icons.sports_soccer,
        ),
        SizedBox(height: 16),
        Text(
          'هذه المباريات أمثلة لتصميم التطبيق وليست جدول مباريات حقيقيًا.',
          style: TextStyle(color: muted),
        ),
      ],
    );
  }
}

class NewsTab extends StatelessWidget {
  const NewsTab({super.key});

  @override
  Widget build(BuildContext context) {
    return ListView(
      padding: const EdgeInsets.all(16),
      children: const [
        SectionTitle(title: 'أخبار كرة القدم'),
        SizedBox(height: 12),
        NewsCard(
          title: 'أخبار الدوري المصري',
          description: 'سيظهر هنا محتوى الأخبار بعد ربط مصدر موثوق.',
          icon: Icons.article,
        ),
        SizedBox(height: 12),
        NewsCard(
          title: 'أخبار الدوري الإنجليزي',
          description: 'أخبار الأندية واللاعبين ونتائج المنافسات.',
          icon: Icons.public,
        ),
        SizedBox(height: 12),
        NewsCard(
          title: 'أخبار الانتقالات',
          description: 'آخر أخبار انتقالات اللاعبين عند توفر البيانات.',
          icon: Icons.swap_horiz,
        ),
      ],
    );
  }
}

class LeagueTab extends StatelessWidget {
  const LeagueTab({super.key});

  final List<Map<String, dynamic>> teams = const [
    {'name': 'الأهلي', 'points': 0},
    {'name': 'الزمالك', 'points': 0},
    {'name': 'بيراميدز', 'points': 0},
    {'name': 'المصري', 'points': 0},
    {'name': 'الإسماعيلي', 'points': 0},
  ];

  @override
  Widget build(BuildContext context) {
    return ListView(
      padding: const EdgeInsets.all(16),
      children: [
        const SectionTitle(title: 'ترتيب الدوري المصري'),
        const SizedBox(height: 8),
        const Text(
          'جدول تجريبي للتصميم فقط',
          style: TextStyle(color: muted),
        ),
        const SizedBox(height: 12),
        Container(
          decoration: BoxDecoration(
            color: panel,
            borderRadius: BorderRadius.circular(16),
          ),
          child: Column(
            children: [
              const Padding(
                padding: EdgeInsets.all(14),
                child: Row(
                  children: [
                    Expanded(
                      flex: 4,
                      child: Text(
                        'الفريق',
                        style: TextStyle(color: green),
                      ),
                    ),
                    Expanded(
                      child: Text(
                        'النقاط',
                        textAlign: TextAlign.center,
                        style: TextStyle(color: green),
                      ),
                    ),
                  ],
                ),
              ),
              const Divider(height: 1, color: bg),
              for (int i = 0; i < teams.length; i++)
                ListTile(
                  leading: CircleAvatar(
                    backgroundColor: green.withAlpha(38),
                    child: Text(
                      '${i + 1}',
                      style: const TextStyle(color: green),
                    ),
                  ),
                  title: Text(teams[i]['name'] as String),
                  trailing: Text(
                    '${teams[i]['points']}',
                    style: const TextStyle(
                      color: green,
                      fontWeight: FontWeight.bold,
                    ),
                  ),
                ),
            ],
          ),
        ),
      ],
    );
  }
}

class SectionTitle extends StatelessWidget {
  final String title;

  const SectionTitle({super.key, required this.title});

  @override
  Widget build(BuildContext context) {
    return Row(
      children: [
        Container(
          width: 4,
          height: 24,
          decoration: BoxDecoration(
            color: green,
            borderRadius: BorderRadius.circular(4),
          ),
        ),
        const SizedBox(width: 8),
        Text(
          title,
          style: const TextStyle(
            fontSize: 18,
            fontWeight: FontWeight.bold,
          ),
        ),
      ],
    );
  }
}

class MatchCard extends StatelessWidget {
  final String home;
  final String away;
  final String score;
  final String status;
  final IconData homeIcon;
  final IconData awayIcon;

  const MatchCard({
    super.key,
    required this.home,
    required this.away,
    required this.score,
    required this.status,
    required this.homeIcon,
    required this.awayIcon,
  });

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: const EdgeInsets.only(bottom: 12),
      padding: const EdgeInsets.all(14),
      decoration: BoxDecoration(
        color: panel,
        borderRadius: BorderRadius.circular(16),
        border: Border.all(color: Colors.white10),
      ),
      child: Column(
        children: [
          Text(
            status,
            style: const TextStyle(color: muted, fontSize: 12),
          ),
          const SizedBox(height: 14),
          Row(
            children: [
              Expanded(
                child: Column(
                  children: [
                    Icon(homeIcon, color: green, size: 30),
                    const SizedBox(height: 8),
                    Text(
                      home,
                      textAlign: TextAlign.center,
                      style: const TextStyle(fontWeight: FontWeight.bold),
                    ),
                  ],
                ),
              ),
              Text(
                score,
                style: const TextStyle(
                  color: green,
                  fontSize: 22,
                  fontWeight: FontWeight.bold,
                ),
              ),
              Expanded(
                child: Column(
                  children: [
                    Icon(awayIcon, color: green, size: 30),
                    const SizedBox(height: 8),
                    Text(
                      away,
                      textAlign: TextAlign.center,
                      style: const TextStyle(fontWeight: FontWeight.bold),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ],
      ),
    );
  }
}

class NewsCard extends StatelessWidget {
  final String title;
  final String description;
  final IconData icon;

  const NewsCard({
    super.key,
    required this.title,
    required this.description,
    required this.icon,
  });

  @override
  Widget build(BuildContext context) {
    return Container(
      padding: const EdgeInsets.all(14),
      decoration: BoxDecoration(
        color: panel,
        borderRadius: BorderRadius.circular(14),
      ),
      child: Row(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Container(
            padding: const EdgeInsets.all(10),
            decoration: BoxDecoration(
              color: green.withAlpha(31),
              borderRadius: BorderRadius.circular(12),
            ),
            child: Icon(icon, color: green, size: 28),
          ),
          const SizedBox(width: 12),
          Expanded(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  title,
                  style: const TextStyle(
                    fontWeight: FontWeight.bold,
                    fontSize: 16,
                  ),
                ),
                const SizedBox(height: 6),
                Text(
                  description,
                  style: const TextStyle(color: muted, height: 1.5),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}