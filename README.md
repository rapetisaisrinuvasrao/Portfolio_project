# MY NAME IS RAPETI SAI SRINUVAS RAO 


base = Path("/mnt/data")
photo_src = base / "1000389161.png"
out_dir = base / "portfolio_readme_package"
assets_dir = out_dir / "assets"
assets_dir.mkdir(parents=True, exist_ok=True)

readme = """# SAI SRINUVAS RAO RAPETI

### Entry-Level Full Stack Developer | React.js | Node.js | Python | AWS | DevOps Fundamentals

<p align="center">
  <img src="./assets/profile-photo.png" alt="Sai Srinivas Rao Rapeti" width="260" />
</p>

<p align="center">
  <a href="https://portfoliorapeti.ccbp.tech/">Portfolio</a> ·
  <a href="https://www.linkedin.com/in/sai-srinuvas-rao-rapeti-164831318/">LinkedIn</a> ·
  <a href="https://github.com/rapetisaisrinuvasrao">GitHub</a>
</p>

---

## About Me

I'm an entry-level Full Stack Developer with a B.Tech in Computer Science and Engineering from Parul University. I have hands-on academic and project experience with HTML, CSS, JavaScript, React.js, Node.js, Python, SQL, Git, GitHub, and AWS.

I've worked on responsive web projects including a food-ordering website, a tourism website, and a real-time chat application. I also have exposure to Linux/Ubuntu, networking, SOC analysis, and DevOps fundamentals. I'm interested in building useful web applications and continuing to grow in full-stack development.

- **Location:** Anakapalli, Andhra Pradesh, India
- **Education:** B.Tech, Computer Science & Engineering — Parul University (2025)
- **Current focus:** Full Stack Development, React.js, Node.js, cloud and DevOps fundamentals

## Technical Skills

| Area | Skills |
|---|---|
| Programming | Python, JavaScript, Core Java, SQL |
| Frontend | HTML, CSS, React.js |
| Backend | Node.js, Full Stack Development, MEAN Full Stack |
| Tools & Cloud | Git, GitHub, AWS, Linux, Ubuntu |
| Other | Networking, SOC Analysis, DevOps Fundamentals |

## Projects

### Foodmunch Website
**May 2025**
- Developed a food-ordering website focused on presenting food items and enabling users to explore and order food.
- Applied web-development fundamentals to create a user-focused website experience.

### Tourism Website
**May 2025**
- Developed a tourism website focused on trip planning and presenting travel information.
- Applied frontend web-development concepts to organize and present travel-related content.

### Real-Time Chat Application
**September 2024 – November 2024**
- Developed a real-time chat application demonstrating web-development and application-building fundamentals.
- Applied programming and web-development concepts while building the application.

## Experience

### SOC Analyst — Parul University
**September 2024 – February 2025**
- Monitored security events and analyzed security-related activities in an academic environment.
- Supported threat detection and incident investigation activities.
- Performed SIEM-based analysis to examine security events and potential incidents.

## Education

**B.Tech — Computer Science & Engineering**  
Parul University, Gujarat · 2025 · 65.8%

**MPC**  
Narayana Junior College, Anakapalli · 2021

**10th Class**  
Chadavaram Chalapathi Public School · 2019

## Certifications

- Cisco Networking Essentials — Cisco Networking Academy
- Basics of Python — Infosys Springboard

## Languages

Telugu · Hindi · English

## Connect With Me

- **Portfolio:** [portfoliorapeti.ccbp.tech](https://portfoliorapeti.ccbp.tech/)
- **LinkedIn:** [Sai Srinuvas Rao Rapeti](https://www.linkedin.com/in/sai-srinuvas-rao-rapeti-164831318/)
- **GitHub:** [@rapetisaisrinuvasrao](https://github.com/rapetisaisrinuvasrao)
- **Email:** [rapetisaisrinuvasrao@gmail.com](mailto:rapetisaisrinuvasrao@gmail.com)

---

<p align="center">
  <i>README presentation inspired by the visual direction of the
  <a href="https://github.com/lohithadamisetti123/premium-portfolio">Premium Portfolio</a> project.</i>
</p>
"""

(out_dir / "README.md").write_text(readme, encoding="utf-8")
if not photo_src.exists():
    raise FileNotFoundError("The uploaded profile photo could not be found.")
shutil.copy2(photo_src, assets_dir / "profile-photo.png")

readme_path = base / "README.md"
readme_path.write_text(readme, encoding="utf-8")

zip_path = base / "Portfolio_project_README_package.zip"
with ZipFile(zip_path, "w", ZIP_DEFLATED) as z:
    z.write(out_dir / "README.md", "README.md")
    z.write(assets_dir / "profile-photo.png", "assets/profile-photo.png")

print(f"Created: {readme_path}")
print(f"Created: {zip_path}")
