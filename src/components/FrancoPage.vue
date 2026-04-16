<template>
  <div class="page-wrapper">
    <div class="card">
      <!-- Header / Banner -->
      <div class="banner">
        <img :src="bannerImg" alt="Burger banner" class="banner-img" />
        <button class="subscribe-btn" @click="showModal = true">
          <span class="subscribe-icon">🔔</span> SUBSCRIBE
        </button>
        <button class="share-btn" @click="showShareModal = true">
          <ShareIcon />
        </button>
      </div>

      <!-- Avatar -->
      <div class="avatar-wrapper">
        <div class="avatar">
          <img :src="avatarImg" alt="Logo Franco" />
        </div>
      </div>

      <!-- Profile Info -->
      <div class="profile-info">
        <h1 class="username">francoesfranco_ve</h1>
        <a href="https://instagram.com/francoesfranco_ve" target="_blank" class="instagram-link">
          <InstagramIcon />
        </a>
        <p class="bio">¡Más de 38 años ofreciendo el Autentico Sabor de Calle!</p>
      </div>

      <!-- Links -->
      <div class="links">
        <a v-for="link in links" :key="link.label" :href="link.href" target="_blank" class="link-btn">
          <span class="link-label">{{ link.label }}</span>
          <span class="link-sub">{{ link.sub }}</span>
        </a>
      </div>

      <!-- Footer -->
      <div class="footer">
        <span class="beacons-logo">⬡ Beacons</span>
      </div>
    </div>

    <!-- ── Modal VIP (Subscribe) ── -->
    <Transition name="fade">
      <div v-if="showModal" class="modal-overlay" @click.self="showModal = false">
        <div class="modal">
          <button class="modal-close" @click="showModal = false">✕</button>
          <div class="modal-logo">
            <img :src="avatarImg" alt="Logo Franco" />
          </div>
          <p class="modal-title">Subscribe to francoesfranco_ve</p>
          <div class="modal-form-box">
            <p class="vip-title">¿Eres cliente VIP?</p>
            <p class="vip-subtitle">Ingresa la información requerida</p>
            <div class="vip-form">
              <input v-model="form.name" type="text" placeholder="Full Name" class="vip-input" />
              <input v-model="form.email" type="email" placeholder="Email" class="vip-input" />
              <input v-model="form.phone" type="tel" placeholder="Phone Number" class="vip-input" />
              <button class="subscribe-dark-btn" @click="handleSubscribe">Subscribe</button>
            </div>
          </div>
        </div>
      </div>
    </Transition>

    <!-- ── Modal Share ── -->
    <Transition name="fade">
      <div v-if="showShareModal" class="modal-overlay" @click.self="showShareModal = false">
        <div class="modal share-modal">
          <button class="modal-close" @click="showShareModal = false">✕</button>

          <div class="modal-logo">
            <img :src="avatarImg" alt="Logo Franco" />
          </div>

          <p class="share-title">SHARE @FRANCOESFRANCO_VE'S BEACONS</p>

          <!-- URL copiable -->
          <div class="share-url-row">
            <div class="share-url-icon">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>
            </div>
            <span class="share-url-text">beacons.ai/francoesfranco_ve</span>
            <button class="share-copy-btn" @click="copyUrl">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="#999"><path d="M16 1H4c-1.1 0-2 .9-2 2v14h2V3h12V1zm3 4H8c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h11c1.1 0 2-.9 2-2V7c0-1.1-.9-2-2-2zm0 16H8V7h11v14z"/></svg>
            </button>
          </div>

          <!-- Opciones de compartir -->
          <div class="share-options">
            <a v-for="opt in shareOptions" :key="opt.label" :href="opt.href" target="_blank" class="share-option-row">
              <div class="share-opt-icon" :style="{ background: opt.color }">
                <span v-html="opt.icon"></span>
              </div>
              <span class="share-opt-label">{{ opt.label }}</span>
              <svg class="share-opt-arrow" width="16" height="16" viewBox="0 0 24 24" fill="#bbb"><path d="M19 19H5V5h7V3H5a2 2 0 00-2 2v14a2 2 0 002 2h14a2 2 0 002-2v-7h-2v7zM14 3v2h3.59l-9.83 9.83 1.41 1.41L19 6.41V10h2V3h-7z"/></svg>
            </a>
          </div>

          <!-- Footer Beacons -->
          <div class="share-footer">
            <div class="share-footer-top">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="#111"><circle cx="12" cy="12" r="10"/></svg>
              <div>
                <p class="share-footer-title">Create your own website on Beacons for free!</p>
                <p class="share-footer-sub">Join 6M+ Beacons users today.</p>
              </div>
            </div>
            <div class="share-footer-btns">
              <button class="share-signup-btn">Sign up</button>
              <button class="share-learn-btn">Learn more</button>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </div>
</template>

<script setup lang="ts">
import { reactive, ref } from "vue";
import bannerImg from "../assets/imagen.jpeg";
import avatarImg from "../assets/logo.jfif";

const showModal = ref<boolean>(false);
const showShareModal = ref<boolean>(false);

const pageUrl = "https://beacons.ai/francoesfranco_ve";

function copyUrl(): void {
  navigator.clipboard.writeText(pageUrl).then(() => {
    alert("¡URL copiada al portapapeles!");
  });
}

const ShareIcon = {
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="white" viewBox="0 0 24 24">
      <path d="M18 16.08c-.76 0-1.44.3-1.96.77L8.91 12.7c.05-.23.09-.46.09-.7s-.04-.47-.09-.7l7.05-4.11c.54.5 1.25.81 2.04.81 1.66 0 3-1.34 3-3s-1.34-3-3-3-3 1.34-3 3c0 .24.04.47.09.7L8.04 9.81C7.5 9.31 6.79 9 6 9c-1.66 0-3 1.34-3 3s1.34 3 3 3c.79 0 1.5-.31 2.04-.81l7.12 4.16c-.05.21-.08.43-.08.65 0 1.61 1.31 2.92 2.92 2.92s2.92-1.31 2.92-2.92-1.31-2.92-2.92-2.92z"/>
    </svg>
  `,
};

const InstagramIcon = {
  template: `
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="white" viewBox="0 0 24 24">
      <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
    </svg>
  `,
};

interface ShareOption {
  label: string;
  href: string;
  color: string;
  icon: string;
}

const shareOptions: ShareOption[] = [
  {
    label: "Share on Facebook",
    href: `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(pageUrl)}`,
    color: "#1877F2",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"/></svg>`,
  },
  {
    label: "Share on LinkedIn",
    href: `https://www.linkedin.com/sharing/share-offsite/?url=${encodeURIComponent(pageUrl)}`,
    color: "#0A66C2",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>`,
  },
  {
    label: "Share on Twitter",
    href: `https://twitter.com/intent/tweet?url=${encodeURIComponent(pageUrl)}`,
    color: "#000000",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>`,
  },
  {
    label: "Share via WhatsApp",
    href: `https://api.whatsapp.com/send?text=${encodeURIComponent(pageUrl)}`,
    color: "#25D366",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>`,
  },
  {
    label: "Share via Messenger",
    href: `https://www.facebook.com/dialog/send?link=${encodeURIComponent(pageUrl)}&app_id=181374005738345`,
    color: "#7B68EE",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M12 2C6.477 2 2 6.145 2 11.243c0 2.908 1.438 5.504 3.688 7.205V22l3.37-1.85c.9.249 1.853.384 2.942.384 5.523 0 10-4.145 10-9.243S17.523 2 12 2zm1.007 12.435l-2.552-2.72-4.98 2.72 5.474-5.81 2.616 2.72 4.916-2.72-5.474 5.81z"/></svg>`,
  },
  {
    label: "Share via Email",
    href: `mailto:?subject=Visita%20francoesfranco_ve&body=${encodeURIComponent(pageUrl)}`,
    color: "#555555",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>`,
  },
  {
    label: "Report page",
    href: "#",
    color: "#E53935",
    icon: `<svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M14.4 6L14 4H5v17h2v-7h5.6l.4 2h7V6z"/></svg>`,
  },
];

interface Link {
  label: string;
  sub: string;
  href: string;
}

const links: Link[] = [
  {
    label: "Whatsapp",
    sub: "Atención al cliente · Delivery · Pick up",
    href: "https://api.whatsapp.com/send?phone=584246743776&text=%C2%A1Hola!%20Vengo%20de%20Instagram%20y%20deseo%20realizar%20un%20pedido%20%E2%9D%A4%EF%B8%8F",
  },
  {
    label: "Menú",
    sub: "Consulta el menú y precios.",
    href: "https://drive.google.com/file/d/1fsuFp0ZyIXj1nhlO1X3zyqO_YKBGSrXU/view",
  },
  {
    label: "Promociones",
    sub: "Consulta de promociones activas.",
    href: "https://drive.google.com/file/d/1Imy_U4RCKF476rfz1y0vcpj2PK8g_ktW/view",
  },
  {
    label: "Franco Eventos",
    sub: "Información del correo para eventos.",
    href: "https://api.whatsapp.com/send?phone=584246282551&text=%C2%A1Hola!%20%C2%BFC%C3%B3mo%20estas%3F%20Vengo%20de%20instagram%20y%20me%20gustar%C3%ADa%20conocer%20informaci%C3%B3n%20acerca%20del%20carrito%20para%20eventos%2C%20gracias.",
  },
  {
    label: "Comparte tu Experiencia",
    sub: "Deja comentarios y solicitudes",
    href: "https://docs.google.com/forms/d/e/1FAIpQLSfyhya8w0UFibcRsnyitHhn--n_0XM4Q855vffC_AtTw4Ifog/viewform",
  },
];

interface Form {
  name: string;
  email: string;
  phone: string;
}

const form = reactive<Form>({ name: "", email: "", phone: "" });

function handleSubscribe(): void {
  if (!form.name || !form.email || !form.phone) {
    alert("Por favor completa todos los campos.");
    return;
  }
  alert(`¡Gracias, ${form.name}! Te registraste como cliente VIP.`);
  form.name = "";
  form.email = "";
  form.phone = "";
  showModal.value = false;
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap");

* { box-sizing: border-box; margin: 0; padding: 0; }

.page-wrapper {
  min-height: 100vh;
  background: linear-gradient(135deg, #e8a87c 0%, #c9a96e 25%, #8fbc6e 50%, #c9a96e 75%, #e8b84b 100%);
  display: flex; 
  align-items: center; 
  justify-content: center;
  font-family: "Poppins", sans-serif; 
  padding: 20px;
}

.card {
  width: 100%; 
  max-width: 360px; 
  background: #1a1a1a;
  border-radius: 24px; 
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5); 
  padding-bottom: 20px;
}

/* Banner */
.banner { position: relative; 
    width: 100%; 
    height: 165px; 
    overflow: hidden; }
.banner-img { width: 100%; 
    height: 100%; 
    object-fit: cover; }

.subscribe-btn {
  position: absolute; 
  top: 12px; 
  left: 12px;
  background: rgba(30,30,30,0.85); 
  color: #fff; 
  border: none;
  border-radius: 20px; 
  padding: 5px 12px; 
  font-size: 11px; 
  font-weight: 600;
  font-family: "Poppins", sans-serif; 
  cursor: pointer;
  display: flex; 
  align-items: center; 
  gap: 5px; 
  letter-spacing: 0.5px;
  transition: background 0.2s;
}
.subscribe-btn:hover { background: rgba(50,50,50,0.95); }
.subscribe-icon { font-size: 12px; }

.share-btn {
  position: absolute; 
  top: 12px; 
  right: 12px;
  background: rgba(30,30,30,0.85); 
  border: none; 
  border-radius: 50%;
  width: 32px; 
  height: 32px; 
  display: flex; 
  align-items: center;
  justify-content: center; 
  cursor: pointer; 
  transition: background 0.2s;
}
.share-btn:hover { background: rgba(50,50,50,0.95); }

/* Avatar */
.avatar-wrapper {
     display: flex; 
     justify-content: center; 
     margin-top: -36px; position: relative; 
     z-index: 10; }
.avatar {
  width: 72px; 
  height: 72px; 
  border-radius: 50%;
  border: 3px solid #2a2a2a; 
  overflow: hidden; background: #f5a623;
}
.avatar img { 
    width: 100%; 
    height: 100%; 
    object-fit: cover; }

/* Profile */
.profile-info { 
    text-align: center; 
    padding: 8px 20px 0; }
.username { 
    color: #fff; 
    font-size: 15px; 
    font-weight: 600; 
    margin-bottom: 6px; }
.instagram-link { 
    display: inline-flex; 
    align-items: center; 
    margin-bottom: 8px; 
    opacity: 0.85; 
    transition: opacity 0.2s; }
.instagram-link:hover { opacity: 1; }
.bio { 
    color: #ccc; 
    font-size: 12px; 
    line-height: 1.4; 
    margin-bottom: 4px; }

/* Links */
.links { 
    padding: 14px 18px 0; 
    display: flex; 
    flex-direction: column; 
    gap: 10px; }
.link-btn {
  display: flex; 
  flex-direction: column; 
  align-items: center; 
  justify-content: center;
  background: #2a2a2a; 
  border: 1px solid #3a3a3a; 
  border-radius: 50px;
  padding: 10px 20px; 
  text-decoration: none; 
  transition: background 0.2s, 
  transform 0.15s;
}
.link-btn:hover { 
    background: #333; 
    transform: translateY(-1px); }
.link-label { 
    color: #fff; 
    font-size: 13px; 
    font-weight: 600; }
.link-sub { 
    color: #999; 
    font-size: 10px; 
    margin-top: 1px; }

/* Footer */
.footer { 
    text-align: center; 
    padding: 20px 0 4px; }
.beacons-logo { 
    color: #666; 
    font-size: 12px; 
    font-weight: 500; 
    display: inline-flex; 
    align-items: center; 
    gap: 4px; }

/* ── MODALS OVERLAY ── */
.modal-overlay {
  position: fixed; 
  inset: 0; 
  background: rgba(0, 0, 0, 0.55);
  display: flex; 
  align-items: center; 
  justify-content: center;
  z-index: 1000; 
  padding: 20px;
}

/* ── VIP Modal ── */
.modal {
  background: #fff; 
  border-radius: 20px; 
  width: 100%; max-width: 400px;
  padding: 28px 24px; 
  position: relative; 
  display: flex;
  flex-direction: column; 
  align-items: center; 
  box-shadow: 0 24px 60px rgba(0,0,0,0.3);
}

.modal-close {
  position: absolute; 
  top: 16px; 
  right: 16px; 
  background: none; 
  border: none;
  font-size: 18px; 
  color: #555; 
  cursor: pointer; 
  padding: 4px;
  transition: color 0.2s; 
  line-height: 1;
}
.modal-close:hover { 
    color: #111; 
}

.modal-logo {
  width: 80px; 
  height: 80px; 
  border-radius: 50%; 
  overflow: hidden;
  margin-bottom: 14px; 
  border: 3px solid #f0f0f0;
}
.modal-logo img { 
    width: 100%; 
    height: 100%; 
    object-fit: cover; }

.modal-title { 
    font-size: 15px; 
    font-weight: 700; 
    color: #111111; 
    margin-bottom: 18px; 
    text-align: center; }

.modal-form-box { 
    width: 100%; 
    border: 1.5px solid #e0e0e0; 
    border-radius: 16px; 
    padding: 20px 18px; }
.vip-title { 
    color: #111; 
    font-size: 16px; 
    font-weight: 700; 
    text-align: center; 
    margin-bottom: 4px; }
.vip-subtitle { 
    color: #888; 
    font-size: 12px; 
    text-align: center; 
    margin-bottom: 14px; }
.vip-form { 
    display: flex; 
    flex-direction: column; 
    gap: 10px; }

.vip-input {
  background: #fff; 
  border: 1.5px solid #d0d0d0; 
  border-radius: 50px;
  color: #111111; 
  font-family: "Poppins", sans-serif; 
  font-size: 13px;
  padding: 11px 18px; 
  outline: none; 
  transition: border-color 0.2s; 
  width: 100%;
}
.vip-input::placeholder { 
    color: #aaa; 
}
.vip-input:focus { 
    border-color: #888; 
}

.subscribe-dark-btn {
  background: #3a3a3a; 
  color: #fff; 
  border: none; 
  border-radius: 50px; 
  padding: 12px;
  font-family: "Poppins", 
  sans-serif; font-size: 14px; 
  font-weight: 600;
  cursor: pointer; 
  transition: background 0.2s, transform 0.15s; 
  width: 100%; margin-top: 4px;
}
.subscribe-dark-btn:hover { 
    background: #222; 
    transform: translateY(-1px); 
}

/* ── Share Modal ── */
.share-modal {
  padding: 24px 0 0;
  max-height: 90vh;
  overflow-y: auto;
}

.share-title {
  font-size: 13px; 
  font-weight: 800; 
  color: #111;
  text-align: center; 
  margin-bottom: 16px;
  padding: 0 24px; 
  letter-spacing: 0.3px;
}

.share-url-row {
  display: flex; 
  align-items: center; 
  gap: 12px;
  padding: 14px 20px; 
  border-top: 1px solid #eee; 
  border-bottom: 1px solid #eee;
  width: 100%; 
  margin-bottom: 4px;
}
.share-url-icon {
  width: 36px; 
  height: 36px; 
  border-radius: 10px; 
  background: #111111;
  display: flex; 
  align-items: center; 
  justify-content: center; 
  flex-shrink: 0;
}
.share-url-text { 
    flex: 1; font-size: 13px; 
    font-weight: 500; 
    color: #111; 
}
.share-copy-btn { 
    background: none; 
    border: none; 
    cursor: pointer; 
    padding: 4px; 
    display: flex; 
    align-items: center; 
}

.share-options { 
    width: 100%; 
    display: flex; 
    flex-direction: column; 
}

.share-option-row {
  display: flex; 
  align-items: center; 
  gap: 14px;
  padding: 14px 20px; 
  text-decoration: none;
  border-bottom: 1px solid #f0f0f0; 
  transition: background 0.15s;
}
.share-option-row:hover { 
    background: #fafafa; 
}

.share-opt-icon {
  width: 36px; 
  height: 36px; 
  border-radius: 10px;
  display: flex; 
  align-items: center; 
  justify-content: center; 
  flex-shrink: 0;
}
.share-opt-label { 
    flex: 1; 
    font-size: 14px; 
    font-weight: 500; 
    color: #111; 
}
.share-opt-arrow { 
    flex-shrink: 0; 
}

/* Share footer */
.share-footer {
  width: 100%; 
  padding: 16px 20px;
  border-top: 1px solid #eee; 
  background: #fafafa;
  border-radius: 0 0 20px 20px;
}
.share-footer-top { 
    display: flex; 
    align-items: center; 
    gap: 10px; margin-bottom: 12px; }
.share-footer-title { 
    font-size: 13px; 
    font-weight: 700; 
    color: #111; 
}
.share-footer-sub { 
    font-size: 11px; 
    color: #888; 
    margin-top: 2px; 
}
.share-footer-btns { 
    display: flex; 
    gap: 10px; 
}
.share-signup-btn {
  flex: 1; 
  background: #111; 
  color: #fff; 
  border: none; 
  border-radius: 50px;
  padding: 12px; 
  font-family: "Poppins", sans-serif; 
  font-size: 13px;
  font-weight: 600; 
  cursor: pointer; 
  transition: background 0.2s;
}
.share-signup-btn:hover { 
    background: #333; 
}
.share-learn-btn {
  flex: 1; 
  background: #fff; 
  color: #111; 
  border: 1.5px solid #ddd;
  border-radius: 50px; 
  padding: 12px; 
  font-family: "Poppins", sans-serif;
  font-size: 13px; 
  font-weight: 600; 
  cursor: pointer; 
  transition: background 0.2s;
}
.share-learn-btn:hover { 
    background: #f0f0f0; 
}

/* Transition */
.fade-enter-active, .fade-leave-active { 
    transition: opacity 0.25s ease; 
}
.fade-enter-from, .fade-leave-to { 
    opacity: 0; 
    }
</style>