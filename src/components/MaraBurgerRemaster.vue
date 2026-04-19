<template>
  <div class="container-c">
    <div class="portada">
      <div class="suscribe" @click="abrirModalSuscripcion">🔔 SUBSCRIBE</div>
      <div class="share" @click="abrirModalCompartir">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M13.803 5.33333C13.803 3.49238 15.3022 2 17.1515 2C19.0008 2 20.5 3.49238 20.5 5.33333C20.5 
              7.17428 19.0008 8.66667 17.1515 8.66667C16.2177 8.66667 15.3738 8.28596 14.7671 7.67347L10.1317 
              10.8295C10.1745 11.0425 10.197 11.2625 10.197 11.4872C10.197 11.9322 10.109 12.3576 9.94959 
              12.7464L15.0323 16.0858C15.6092 15.6161 16.3473 15.3333 17.1515 15.3333C19.0008 15.3333 20.5 16.8257 
              20.5 18.6667C20.5 20.5076 19.0008 22 17.1515 22C15.3022 22 13.803 20.5076 13.803 18.6667C13.803 18.1845 
              13.9062 17.7255 14.0917 17.3111L9.05007 13.9987C8.46196 14.5098 7.6916 14.8205 6.84848 14.8205C4.99917 
              14.8205 3.5 13.3281 3.5 11.4872C3.5 9.64623 4.99917 8.15385 6.84848 8.15385C7.9119 8.15385 8.85853 8.64725 
              9.47145 9.41518L13.9639 6.35642C13.8594 6.03359 13.803 5.6896 13.803 5.33333Z"
              fill="#1C274C">
            </path>
          </g>
        </svg>
      </div>

    </div>

    <div class="user">
      <h4>MaraBurguer_ve</h4>

      <!-- ── Instagram con link funcional ── -->
      <a
        href="https://www.instagram.com/maraburguer_ve"
        target="_blank"
        rel="noopener noreferrer"
        class="ig-link"
      >
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
          <g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g>
          <g id="SVGRepo_iconCarrier">
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M12 18C15.3137 18 18 15.3137 18 12C18 8.68629 15.3137 6 12 6C8.68629 6 6 8.68629 6 12C6 15.3137 
              8.68629 18 12 18ZM12 16C14.2091 16 16 14.2091 16 12C16 9.79086 14.2091 8 12 8C9.79086 8 8 9.79086 8 
              12C8 14.2091 9.79086 16 12 16Z" fill="white">
            </path>
            <path d="M18 5C17.4477 5 17 5.44772 17 6C17 6.55228 17.4477 7 18 7C18.5523 7 19 6.55228 19 6C19 5.44772 18.5523 5 18 5Z"
              fill="white">
            </path>
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M1.65396 4.27606C1 5.55953 1 7.23969 1 10.6V13.4C1 16.7603 1 18.4405 1.65396 19.7239C2.2292 20.8529 
              3.14708 21.7708 4.27606 22.346C5.55953 23 7.23969 23 10.6 23H13.4C16.7603 23 18.4405 23 19.7239 22.346C20.8529 
              21.7708 21.7708 20.8529 22.346 19.7239C23 18.4405 23 16.7603 23 13.4V10.6C23 7.23969 23 5.55953 22.346 
              4.27606C21.7708 3.14708 20.8529 2.2292 19.7239 1.65396C18.4405 1 16.7603 1 13.4 1H10.6C7.23969 1 5.55953 
              1 4.27606 1.65396C3.14708 2.2292 2.2292 3.14708 1.65396 4.27606ZM13.4 3H10.6C8.88684 3 7.72225 3.00156 
              6.82208 3.0751C5.94524 3.14674 5.49684 3.27659 5.18404 3.43597C4.43139 3.81947 3.81947 4.43139 3.43597 
              5.18404C3.27659 5.49684 3.14674 5.94524 3.0751 6.82208C3.00156 7.72225 3 8.88684 3 10.6V13.4C3 15.1132 
              3.00156 16.2777 3.0751 17.1779C3.14674 18.0548 3.27659 18.5032 3.43597 18.816C3.81947 19.5686 4.43139 
              20.1805 5.18404 20.564C5.49684 20.7234 5.94524 20.8533 6.82208 20.9249C7.72225 20.9984 8.88684 21 10.6 
              21H13.4C15.1132 21 16.2777 20.9984 17.1779 20.9249C18.0548 20.8533 18.5032 20.7234 18.816 20.564C19.5686 
              20.1805 20.1805 19.5686 20.564 18.816C20.7234 18.5032 20.8533 18.0548 20.9249 17.1779C20.9984 16.2777 21 
              15.1132 21 13.4V10.6C21 8.88684 20.9984 7.72225 20.9249 6.82208C20.8533 5.94524 20.7234 5.49684 20.564 
              5.18404C20.1805 4.43139 19.5686 3.81947 18.816 3.43597C18.5032 3.27659 18.0548 3.14674 17.1779 3.0751C16.2777 
              3.00156 15.1132 3 13.4 3Z" fill="white">
            </path>
          </g>
        </svg>
      </a>
    </div>

    <div class="opciones">
      <h2>¡Ofrecemos el Auténtico Sabor Marabino!</h2>

      <a href="https://api.whatsapp.com/send?phone=584129199367&text=%C2%A1Hola!%20Vengo%20de%20Instagram%20y%20deseo%20realizar%20un%20pedido%20%E2%9D%A4%EF%B8%8F" target="_blank">
        <div class="opcion"><h3>WhatsApp</h3><p>Atención al cliente - delivery - Pick up</p></div>
      </a>
      <a href="https://drive.google.com/file/d/1fsuFp0ZyIXj1nhlO1X3zyqO_YKBGSrXU/view" target="_blank">
        <div class="opcion"><h3>Menú</h3><p>Consulta de menú y precios</p></div>
      </a>
      <a href="https://drive.google.com/file/d/1Imy_U4RCKF476rfz1y0vcpj2PK8g_ktW/view" target="_blank">
        <div class="opcion"><h3>Promociones</h3><p>Consulta de promociones activas</p></div>
      </a>
      <a href="https://api.whatsapp.com/send?phone=584129199367&text=%C2%A1Hola!%20%C2%BFC%C3%B3mo%20estas%3F%20Vengo%20de%20instagram%20y%20me%20gustar%C3%ADa%20conocer%20informaci%C3%B3n%20acerca%20del%20carrito%20para%20eventos%2C%20gracias.%20%F0%9F%98%80" target="_blank">
        <div class="opcion"><h3>Mara Eventos</h3><p>Información del carrito para eventos</p></div>
      </a>
      <a href="https://docs.google.com/forms/d/e/1FAIpQLScESFE7gz0krpFhMz6C-oxBkOpv63Kdswieb7r2XVKnAee1fQ/viewform?usp=publish-editor" target="_blank">
        <div class="opcion"><h3>Comparte tu Experiencia</h3><p>Deja comentarios y solicitudes</p></div>
      </a>
    </div>

    <div class="contacto">
      <form @submit.prevent>
        <h1>¿Eres cliente VIP?</h1>
        <h2>Ingresa la información requerida</h2>
        <div><input type="text" placeholder="Full Name" /></div>
        <div><input type="email" placeholder="Email" /></div>
        <div><input type="tel" placeholder="Phone Number" /></div>
        <button type="submit">Suscribirse</button>
      </form>
    </div>

    <!-- ===================== FOOTER BEACONS ===================== -->
    <div class="beacons-footer">
      <a href="https://beacons.ai/signup" target="_blank" class="beacons-footer-link">
        <svg width="26" height="26" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="14" cy="14" r="6" fill="white"/>
          <circle cx="26" cy="14" r="6" fill="white"/>
          <circle cx="14" cy="26" r="6" fill="white"/>
          <circle cx="26" cy="26" r="6" fill="white"/>
        </svg>
        <span>Beacons</span>
      </a>
    </div>

    <!-- ===================== MODAL SUSCRIPCION ===================== -->
    <Teleport to="body">
      <Transition name="fade">
        <div v-if="mostrarSuscripcion" class="modal-overlay" @click.self="cerrarModalSuscripcion">
          <div class="modal-box">
            <button class="modal-close" @click="cerrarModalSuscripcion">✕</button>
            <div class="modal-logo">
              <div class="logo-circle"></div>
            </div>
            <p class="modal-sub-title">Subscribe to <strong>MaraBurguer_ve</strong></p>
            <div class="modal-form-box">
              <h1>¿Eres cliente VIP?</h1>
              <p>Ingresa la información requerida</p>
              <form @submit.prevent="enviarSuscripcion">
                <div><input v-model="suscripcionForm.nombre" type="text" placeholder="Full Name" /></div>
                <div><input v-model="suscripcionForm.email" type="email" placeholder="Email" /></div>
                <div><input v-model="suscripcionForm.telefono" type="tel" placeholder="Phone Number" /></div>
                <button type="submit">Subscribe</button>
              </form>
            </div>
          </div>
        </div>
      </Transition>
    </Teleport>

    <!-- ===================== MODAL COMPARTIR ===================== -->
    <Teleport to="body">
      <Transition name="fade">
        <div v-if="mostrarCompartir" class="modal-overlay" @click.self="cerrarModalCompartir">
          <div class="modal-box">
            <button class="modal-close" @click="cerrarModalCompartir">✕</button>
            <div class="modal-logo">
              <div class="logo-circle"></div>
            </div>
            <p class="modal-share-header">SHARE @MARABURGUER_VE'S BEACONS</p>
            <div class="share-link-box">
              <span class="share-icon-dot">✦</span>
              <span class="share-link-text">beacons.ai/maraburguer_ve</span>
              <button class="copy-btn" @click="copiarEnlace" :class="{ copiado: enlaceCopiado }">
                {{ enlaceCopiado ? '✓' : '⧉' }}
              </button>
            </div>
            <div class="share-options">
              <a :href="shareLinks.facebook" target="_blank" class="share-item">
                <span class="share-item-icon fb-icon">f</span><span>Share on Facebook</span><span class="share-ext">↗</span>
              </a>
              <a :href="shareLinks.linkedin" target="_blank" class="share-item">
                <span class="share-item-icon li-icon">in</span><span>Share on LinkedIn</span><span class="share-ext">↗</span>
              </a>
              <a :href="shareLinks.twitter" target="_blank" class="share-item">
                <span class="share-item-icon tw-icon">𝕏</span><span>Share on Twitter</span><span class="share-ext">↗</span>
              </a>
              <a :href="shareLinks.whatsapp" target="_blank" class="share-item">
                <span class="share-item-icon wa-icon">W</span><span>Share via WhatsApp</span><span class="share-ext">↗</span>
              </a>
              <a :href="shareLinks.messenger" target="_blank" class="share-item">
                <span class="share-item-icon ms-icon">m</span><span>Share via Messenger</span><span class="share-ext">↗</span>
              </a>
              <a :href="shareLinks.email" target="_blank" class="share-item">
                <span class="share-item-icon em-icon">✉</span><span>Share via Email</span><span class="share-ext">↗</span>
              </a>
              <a href="#" class="share-item report-item">
                <span class="share-item-icon rp-icon">⚑</span><span>Report page</span><span class="share-ext">↗</span>
              </a>
            </div>
            <div class="share-footer">
              <div class="share-footer-info">
                <svg width="22" height="22" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0;margin-top:2px">
                  <circle cx="14" cy="14" r="6" fill="#333"/>
                  <circle cx="26" cy="14" r="6" fill="#333"/>
                  <circle cx="14" cy="26" r="6" fill="#333"/>
                  <circle cx="26" cy="26" r="6" fill="#333"/>
                </svg>
                <div>
                  <p class="share-footer-title">Create your own website on Beacons for free!</p>
                  <p class="share-footer-sub">Join 6M+ Beacons users today.</p>
                </div>
              </div>
              <div class="share-footer-btns">
                <a href="https://beacons.ai/signup" target="_blank" class="share-btn-signup">Sign up</a>
                <a href="https://beacons.ai/signup" target="_blank" class="share-btn-learn">Learn more</a>
              </div>
            </div>
          </div>
        </div>
      </Transition>
    </Teleport>

    <!-- ===================== BOTON FLOTANTE BEACONS ===================== -->
    <Teleport to="body">
      <a href="https://beacons.ai/signup" target="_blank" class="beacons-float-btn">
        <svg width="20" height="20" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="14" cy="14" r="6" fill="#111"/>
          <circle cx="26" cy="14" r="6" fill="#111"/>
          <circle cx="14" cy="26" r="6" fill="#111"/>
          <circle cx="26" cy="26" r="6" fill="#111"/>
        </svg>
        <span class="beacons-float-name">Beacons</span>
        <span class="beacons-float-divider"></span>
        <span class="beacons-float-cta">Try for free!</span>
      </a>
    </Teleport>

  </div>
</template>

<script setup lang="ts">
import { ref, reactive, computed } from 'vue'

const mostrarSuscripcion = ref(false)
const mostrarCompartir   = ref(false)
const enlaceCopiado      = ref(false)

const suscripcionForm = reactive({ nombre: '', email: '', telefono: '' })
const paginaUrl = 'https://beacons.ai/maraburguer_ve'

const shareLinks = computed(() => ({
  facebook:  `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(paginaUrl)}`,
  linkedin:  `https://www.linkedin.com/sharing/share-offsite/?url=${encodeURIComponent(paginaUrl)}`,
  twitter:   `https://twitter.com/intent/tweet?url=${encodeURIComponent(paginaUrl)}&text=¡Visita%20MaraBurguer_ve!`,
  whatsapp:  `https://api.whatsapp.com/send?text=${encodeURIComponent('¡Visita MaraBurguer_ve! ' + paginaUrl)}`,
  messenger: `https://www.facebook.com/dialog/send?link=${encodeURIComponent(paginaUrl)}&app_id=YOUR_APP_ID`,
  email:     `mailto:?subject=MaraBurguer_ve&body=${encodeURIComponent('¡Visita MaraBurguer_ve! ' + paginaUrl)}`
}))

function abrirModalSuscripcion() { mostrarSuscripcion.value = true }
function cerrarModalSuscripcion() { mostrarSuscripcion.value = false }
function abrirModalCompartir()   { mostrarCompartir.value = true }
function cerrarModalCompartir()  { mostrarCompartir.value = false }

function enviarSuscripcion() {
  if (!suscripcionForm.nombre || !suscripcionForm.email) {
    alert('Por favor completa los campos requeridos.')
    return
  }
  alert(`¡Gracias ${suscripcionForm.nombre}! Te has suscrito correctamente.`)
  suscripcionForm.nombre   = ''
  suscripcionForm.email    = ''
  suscripcionForm.telefono = ''
  cerrarModalSuscripcion()
}

async function copiarEnlace() {
  try {
    await navigator.clipboard.writeText(paginaUrl)
    enlaceCopiado.value = true
    setTimeout(() => { enlaceCopiado.value = false }, 2000)
  } catch {
    alert('No se pudo copiar. Copia manualmente: ' + paginaUrl)
  }
}
</script>

<style scoped>
/* ========== BASE ========== */
a {
  text-decoration: none;
  color: inherit;
  width: 100%;
  display: flex;
  justify-content: center;
}

.container-c {
  background-color: #101010;
  width: 100%;
  max-width: 700px;
  margin: 80px 10px 80px 10px;
  border-radius: 20px;
}

/* ========== BANNER / PORTADA ========== */
.portada {
  background-image: url("../assets/amburguesa.jpeg");
  background-size: cover;
  background-position: center;
  height: 335px;
  margin: 50px 60px 0 60px;
  border-radius: 20px;
  position: relative;
}

.suscribe {
  position: absolute;
  top: 20px;
  left: 20px;
  background-color: #e0e0e0;
  padding: 10px 20px;
  border-radius: 20px;
  color: gray;
  font-weight: bold;
  cursor: pointer;
  transition: transform 0.2s, background-color 0.2s;
}
.suscribe:hover { transform: scale(1.05); background-color: #ffffff; }

.share {
  position: absolute;
  top: 20px;
  right: 20px;
  background-color: #e0e0e0;
  padding: 10px;
  border-radius: 50%;
  height: 20px;
  width: 20px;
  cursor: pointer;
  transition: transform 0.2s, background-color 0.2s;
}
.share:hover { transform: scale(1.1); background-color: #ffffff; }
.share svg { width: 20px; height: 20px; }

/* ========== USER INFO ========== */
.user {
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 16px;
  gap: 10px;
  padding-bottom: 4px;
}
.user h4 { font-size: 20px; font-weight: bold; }

/* ── Botón Instagram funcional ── */
.ig-link {
  display: inline-flex !important;
  width: auto !important;
  justify-content: center;
  opacity: 0.85;
  transition: opacity 0.2s, transform 0.2s;
}
.ig-link:hover { opacity: 1; transform: scale(1.1); }
.ig-link svg { width: 26px; height: 26px; }

/* ========== OPCIONES / LINKS ========== */
.opciones {
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 8px;
}
.opciones h2 {
  font-size: 16px;
  font-weight: 700;
  text-align: center;
  padding: 0 20px 12px;
}
.opcion {
  border-radius: 40px;
  background-color: #1f2125;
  border: 2px solid white;
  width: 80%;
  margin: 10px 0;
  padding: 12px;
  text-align: center;
  transition: transform 0.2s;
}
.opcion:hover { transform: scale(1.05); }

/* ========== FORMULARIO VIP ========== */
.contacto {
  display: flex;
  justify-content: center;
  border-radius: 20px;
  margin: 20px 0;
}
.contacto form {
  background-color: #1f2125;
  border-radius: 40px;
  padding: 20px;
  width: 80%;
  color: white;
  text-align: center;
}
input {
  border: 2px solid white;
  background-color: transparent;
  box-sizing: border-box;
  color: white;
  font-size: 20px;
  width: 100%;
  margin: 15px 0;
  padding: 12px;
  border-radius: 40px;
}
button {
  background-color: white;
  border: none;
  padding: 20px;
  border-radius: 40px;
  color: black;
  font-weight: bold;
  font-size: 20px;
  cursor: pointer;
  width: 100%;
  transition: transform 0.2s;
}
button:hover { transform: scale(1.04); }

/* ========== FOOTER BEACONS ========== */
.beacons-footer {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px 0 32px 0;
}
.beacons-footer-link {
  display: flex !important;
  align-items: center;
  gap: 10px;
  color: white;
  font-size: 18px;
  font-weight: 600;
  opacity: 0.9;
  transition: opacity 0.2s;
  width: auto;
  justify-content: center !important;
}
.beacons-footer-link:hover { opacity: 1; }

/* ========== MODALES ========== */
.modal-overlay {
  position: fixed;
  inset: 0;
  background-color: rgba(0,0,0,0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 20px;
}
.modal-box {
  background: #ffffff;
  border-radius: 20px;
  padding: 30px 24px;
  width: 100%;
  max-width: 460px;
  position: relative;
  max-height: 90vh;
  overflow-y: auto;
}
.modal-close {
  position: absolute;
  top: 16px; right: 16px;
  background: none; border: none;
  font-size: 18px; cursor: pointer;
  color: #555; padding: 4px 8px;
  width: auto; border-radius: 50%;
  transition: background 0.2s;
}
.modal-close:hover { background: #f0f0f0; transform: none; }

.modal-logo { display: flex; justify-content: center; margin-bottom: 12px; }
.logo-circle {
  width: 70px; height: 70px; border-radius: 50%;
  background-image: url("../assets/logo.jfif");
  background-size: cover; border: 2px solid #ddd;
}
.modal-sub-title { text-align: center; font-size: 15px; color: #333; margin-bottom: 16px; }

/* Modal Suscripción */
.modal-form-box { border: 1.5px solid #ddd; border-radius: 16px; padding: 24px; text-align: center; }
.modal-form-box h1 { font-size: 22px; color: #111; margin-bottom: 6px; }
.modal-form-box p  { font-size: 14px; color: #777; margin-bottom: 12px; }
.modal-form-box input { border: 1.5px solid #ccc; color: #111; font-size: 16px; margin: 8px 0; padding: 14px 18px; }
.modal-form-box input::placeholder { color: #aaa; }
.modal-form-box button { background-color: #333; color: white; font-size: 16px; padding: 16px; margin-top: 8px; }
.modal-form-box button:hover { background-color: #111; }

/* Modal Compartir */
.modal-share-header { text-align: center; font-size: 13px; font-weight: bold; color: #333; letter-spacing: 0.5px; margin-bottom: 14px; }
.share-link-box { display: flex; align-items: center; background: #f5f5f5; border-radius: 12px; padding: 12px 16px; margin-bottom: 14px; gap: 10px; }
.share-icon-dot { font-size: 18px; color: #555; }
.share-link-text { flex: 1; font-size: 14px; color: #333; font-weight: 500; }
.copy-btn { background: #e0e0e0; border: none; border-radius: 8px; padding: 6px 12px; cursor: pointer; font-size: 16px; color: #333; width: auto; transition: background 0.2s; }
.copy-btn:hover { background: #ccc; transform: none; }
.copy-btn.copiado { background: #4caf50; color: white; }

.share-options { display: flex; flex-direction: column; gap: 0; }
.share-item {
  display: flex !important; align-items: center; gap: 14px;
  padding: 14px 4px; border-bottom: 1px solid #f0f0f0;
  color: #1a1a1a; font-size: 15px; font-weight: 400;
  transition: background 0.15s; width: 100%; justify-content: flex-start !important;
}
.share-item:hover { background: #f9f9f9; }
.share-item:last-child { border-bottom: none; }
.share-item span:nth-child(2) { flex: 1; }
.share-ext { font-size: 13px; color: #bbb; flex-shrink: 0; }
.share-item-icon {
  width: 38px; height: 38px; border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 15px; font-weight: 700; color: white; flex-shrink: 0;
}
.fb-icon { background: #1877f2; }
.li-icon { background: #0a66c2; font-size: 12px; }
.tw-icon { background: #000000; font-size: 13px; font-family: serif; }
.wa-icon { background: #25d366; font-size: 16px; }
.ms-icon { background: #0078ff; font-size: 16px; font-style: italic; }
.em-icon { background: #444; font-size: 15px; }
.rp-icon { background: #e53935; font-size: 15px; }
.report-item { color: #555; }

.share-footer { margin-top: 16px; padding-top: 16px; border-top: 1px solid #ebebeb; }
.share-footer-info { display: flex; align-items: flex-start; gap: 10px; margin-bottom: 14px; }
.share-footer-title { font-size: 14px; font-weight: 600; color: #111; margin: 0 0 2px 0; }
.share-footer-sub { font-size: 13px; color: #888; margin: 0; }
.share-footer-btns { display: flex; gap: 10px; }
.share-btn-signup {
  flex: 1; background: #111; color: white !important; border-radius: 30px; padding: 14px 0;
  text-align: center; font-size: 15px; font-weight: 600;
  display: flex; align-items: center; justify-content: center;
  transition: background 0.2s; width: auto;
}
.share-btn-signup:hover { background: #333; }
.share-btn-learn {
  flex: 1; background: #ffffff; color: #111 !important; border: 1.5px solid #ddd;
  border-radius: 30px; padding: 14px 0; text-align: center; font-size: 15px; font-weight: 600;
  display: flex; align-items: center; justify-content: center;
  transition: background 0.2s; width: auto;
}
.share-btn-learn:hover { background: #f5f5f5; }

/* ========== BOTÓN FLOTANTE BEACONS ========== */
.beacons-float-btn {
  position: fixed; bottom: 20px; right: 20px;
  display: flex; align-items: center; gap: 7px;
  background: #f0f0f0; border-radius: 30px; padding: 8px 14px;
  color: #111; font-size: 13px; font-weight: 500;
  box-shadow: 0 2px 10px rgba(0,0,0,0.18); z-index: 9999;
  transition: transform 0.2s, box-shadow 0.2s;
  white-space: nowrap; width: fit-content; max-width: 200px;
}
.beacons-float-btn:hover { transform: scale(1.05); box-shadow: 0 4px 16px rgba(0,0,0,0.25); }
.beacons-float-name { font-weight: 600; color: #111; font-size: 13px; }
.beacons-float-divider { width: 1px; height: 14px; background: #bbb; margin: 0 1px; }
.beacons-float-cta { color: #555; font-weight: 400; font-size: 13px; }

/* ========== TRANSICIÓN ========== */
.fade-enter-active, .fade-leave-active { transition: opacity 0.25s ease; }
.fade-enter-from, .fade-leave-to { opacity: 0; }
</style>