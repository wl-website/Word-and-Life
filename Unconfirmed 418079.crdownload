// Newsletter Data
const nlData = [
  {t:'June 2025 Ministry Update', d:'June 2025', y:'2025', desc:'Recap of teacher training in Kasungu, new Bible study groups launched, and inspiring testimonies.', bg:'linear-gradient(135deg,#0C3460,#1A5276)'},
  {t:'May 2025: New Communities', d:'May 2025', y:'2025', desc:'Expanded to three new villages and celebrated our first life skills cohort graduation.', bg:'linear-gradient(135deg,#1B6B3A,#2E8B57)'},
  {t:'April 2025: Easter Outreach', d:'April 2025', y:'2025', desc:'Our Easter outreach reached over 300 children across 8 communities.', bg:'linear-gradient(135deg,#7B3800,#B06010)'},
  {t:'Q4 2024 Annual Report', d:'December 2024', y:'2024', desc:'A full review of our 2024 year — milestones, testimonies, and God\'s faithfulness.', bg:'linear-gradient(135deg,#09243E,#0C3460)'},
  {t:'November 2024: Training Highlights', d:'November 2024', y:'2024', desc:'60 teachers gathered for a 3-day intensive program in Lilongwe.', bg:'linear-gradient(135deg,#1A5276,#2E86C1)'},
  {t:'September 2023: Ministry Launch', d:'September 2023', y:'2023', desc:'The official launch of Word & Life Empowerment Ministry.', bg:'linear-gradient(135deg,#7B3800,#C8960C)'},
  {t:'December 2023: Year End Report', d:'December 2023', y:'2023', desc:'Our first year in review — lessons learned, lives touched, vision renewed.', bg:'linear-gradient(135deg,#0C3460,#C8960C)'},
];

// Gallery Data - Now using real images
const galData = [
  {c:'trainings', img:'images/gallery-1.jpg', s:'m'},
  {c:'children', img:'images/gallery-2.jpg', s:'l'},
  {c:'bible', img:'images/gallery-3.jpg', s:'s'},
  {c:'outreach', img:'images/gallery-4.jpg', s:'m'},
  {c:'trainings', img:'images/gallery-5.jpg', s:'l'},
  {c:'community', img:'images/gallery-6.jpg', s:'s'},
  {c:'children', img:'images/gallery-7.jpg', s:'m'},
  {c:'bible', img:'images/gallery-8.jpg', s:'l'},
  {c:'outreach', img:'images/gallery-9.jpg', s:'s'},
  {c:'trainings', img:'images/gallery-10.jpg', s:'m'},
  {c:'community', img:'images/gallery-11.jpg', s:'l'},
  {c:'children', img:'images/gallery-12.jpg', s:'s'},
];

// Mobile Menu Toggle
function toggleM() {
  const mm = document.getElementById('mm');
  if (mm) mm.classList.toggle('open');
}

// Scroll Reveal
function reveal() {
  document.querySelectorAll('.rv').forEach(el => {
    if (el.getBoundingClientRect().top < window.innerHeight - 40) {
      el.classList.add('in');
    }
  });
}

window.addEventListener('scroll', reveal);
setTimeout(reveal, 200);

// Donate Modal
function openD() {
  const dm = document.getElementById('dm');
  if (dm) dm.classList.add('on');
}

function selA(btn) {
  document.querySelectorAll('.am').forEach(x => x.classList.remove('sel'));
  btn.classList.add('sel');
}

// Close modal when clicking outside
const dm = document.getElementById('dm');
if (dm) {
  dm.addEventListener('click', function(e) {
    if (e.target === this) this.classList.remove('on');
  });
}

// Newsletter Subscription
function doSub(id) {
  const el = document.getElementById(id);
  if (el && el.value.indexOf('@') > 0) {
    alert('Subscribed!\n' + el.value);
    el.value = '';
  } else {
    alert('Please enter a valid email address.');
  }
}

// Escape key handler
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') {
    const dm = document.getElementById('dm');
    const ulm = document.getElementById('ulm');
    if (dm) dm.classList.remove('on');
    if (ulm) ulm.style.display = 'none';
  }
});

// Newsletter Functions
function renderNL(yr) {
  const filtered = yr === 'all' ? nlData : nlData.filter(n => n.y === yr);
  const container = document.getElementById('nlG');
  if (!container) return;
  container.innerHTML = filtered.map(n => `
    <div class="card nc">
      <div class="ni" style="background:${n.bg};color:rgba(255,255,255,0.5);font-size:2.5rem">📰</div>
      <div class="nb">
        <div class="nd">${n.d}</div>
        <h3>${n.t}</h3>
        <p>${n.desc}</p>
        <div class="nba">
          <button class="btn bB" onclick="alert('Reading: ${n.t}')">Read</button>
          <button class="btn bO" onclick="alert('Downloading PDF: ${n.t}')">Download PDF</button>
        </div>
      </div>
    </div>
  `).join('');
}

function nlF(yr, btn) {
  document.querySelectorAll('#nlT .tab').forEach(b => b.classList.remove('on'));
  btn.classList.add('on');
  renderNL(yr);
}

// Gallery Functions - Using real images
function renderGal(cat) {
  const filtered = cat === 'all' ? galData : galData.filter(g => g.c === cat);
  const container = document.getElementById('galG');
  if (!container) return;
  container.innerHTML = filtered.map(x => `
    <div class="gi">
      <img src="${x.img}" alt="Gallery image" class="gt ${x.s}" style="width:100%; height:100%; object-fit:cover; min-height:${x.s === 's' ? '130px' : x.s === 'm' ? '185px' : '245px'}">
    </div>
  `).join('');
}

function galF(cat, btn) {
  document.querySelectorAll('#galT .tab').forEach(b => b.classList.remove('on'));
  btn.classList.add('on');
  renderGal(cat);
}

// Initialize page-specific content when DOM is ready
document.addEventListener('DOMContentLoaded', function() {
  // Check if we're on newsletter page
  if (document.getElementById('nlG')) {
    renderNL('all');
  }
  // Check if we're on gallery page
  if (document.getElementById('galG')) {
    renderGal('all');
  }
});