```c
#include <stdio.h>

// ANSI escape codes for colors
#define RED     "\033[31m"
#define GREEN   "\033[32m"
#define CYAN    "\033[36m"
#define RESET   "\033[0m"
#define BOLD    "\033[1m"

// 👤 Personal Profile
void personal_profile() {
    printf(BOLD CYAN "👨‍💻 Angel Gonzales Laura\n" RESET);
    printf("🌍 Location: Madrid, Spain\n");
    printf("🔗 LinkedIn: https://linkedin.com/in/angel-gonzales-laura\n");
    printf("🐙 GitHub: https://github.com/hanjelito\n");
    printf("🌐 Web: https://peruyoung.com\n\n");
}

// 🎓 Education
void education() {
    printf(BOLD GREEN "🎓 Education\n" RESET);
    printf("📚 Computer Engineering - UCSP (2003 - 2007)\n");
    printf("📚 Industrial Engineering - Continental University (2016 - 2019)\n");
    printf("🧠 42 Madrid - Low-level Programming (2020 - in progress)\n\n");
}

// 💼 Experience
void work_experience() {
    printf(BOLD GREEN "💼 Work Experience\n" RESET);
    printf("🔧 Independent Consultant - QUASAR / COMEX (2025 - Present)\n");
    printf("🔧 Libertad Digital - Senior Backend Dev (2021 - 2025)\n");
    printf("🔧 APROS / Studio Tigres (2017 - 2021)\n");
    printf("🔧 Apros: Consultores Digitales (2014 - 2017)\n\n");
}

// 🛠 Technical Skills
void technical_skills() {
    printf(BOLD GREEN "🛠 Technical Skills\n" RESET);
    printf("💻 Languages: C, C++, Go, Python, PHP, JavaScript, TS, Kotlin, Bash\n");
    printf("🔧 Tools: Docker, Kubernetes, n8n, Linux, Git, Jira\n");
    printf("🧰 Frameworks: NestJS, Laravel, Symfony, Flutter\n");
    printf("🗄️ Databases: PostgreSQL, MySQL, MongoDB\n");
    printf("☁️ Cloud: AWS, GCP, Azure\n\n");
}

// 🧠 Interests
void interests() {
    printf(BOLD GREEN "📌 Interests\n" RESET);
    printf("⚙️ Workflow automation, System architecture, Data engineering\n");
    printf("☁️ Cloud-native development, DevOps, AI/ML scraping tools\n\n");
}

int main() {
    personal_profile();
    education();
    work_experience();
    technical_skills();
    interests();
    printf(BOLD RED ">>> Compiled with passion and over 20 years of experience! 🔥\n" RESET);
    return 0;
}


```
## Stats
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Hanjelito&theme=tokyonight)
