const header = document.querySelector(".site-header");
const menuButton = document.querySelector(".menu-button");
const navigation = document.querySelector(".primary-nav");
const year = document.querySelector("#year");
const contactForm = document.querySelector("#contact-form");
const formNote = document.querySelector("#form-note");

if (year) year.textContent = new Date().getFullYear();

function setHeaderState() {
  header?.classList.toggle("scrolled", window.scrollY > 24);
}
setHeaderState();
window.addEventListener("scroll", setHeaderState, { passive: true });

menuButton?.addEventListener("click", () => {
  const open = navigation.classList.toggle("open");
  document.body.classList.toggle("menu-open", open);
  menuButton.setAttribute("aria-expanded", String(open));
});

navigation?.querySelectorAll("a").forEach((link) => {
  link.addEventListener("click", () => {
    navigation.classList.remove("open");
    document.body.classList.remove("menu-open");
    menuButton?.setAttribute("aria-expanded", "false");
  });
});

if ("IntersectionObserver" in window) {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.14 });

  document.querySelectorAll(".reveal").forEach((element) => observer.observe(element));
} else {
  document.querySelectorAll(".reveal").forEach((element) => element.classList.add("visible"));
}

contactForm?.addEventListener("submit", (event) => {
  event.preventDefault();

  if (!contactForm.reportValidity()) return;

  const data = new FormData(contactForm);
  const subject = encodeURIComponent(`Unity Pads website enquiry — ${data.get("type")}`);
  const body = encodeURIComponent(
`Name: ${data.get("name") || ""}
Organisation: ${data.get("organisation") || ""}
Email: ${data.get("email") || ""}
Telephone: ${data.get("phone") || ""}
Enquiry type: ${data.get("type") || ""}

Message:
${data.get("message") || ""}`
  );

  window.location.href = `mailto:unitypads@outlook.com?subject=${subject}&body=${body}`;

  if (formNote) {
    formNote.textContent = "Your email application should now open with the enquiry prepared.";
  }
});
