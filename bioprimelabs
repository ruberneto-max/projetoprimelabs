import React, { useEffect, useState } from 'react';
import { Shield, Activity, Dna, Zap, Target, ArrowRight, Microchip, Beaker, ChevronRight } from 'lucide-react';

const GlobalStyles = () => (
  <style>{`
    :root {
      --bioprime-electric-blue: #0E7BFF;
      --bioprime-deep-blue: #050B1F;
      --bioprime-neon-green: #39FF5A;
      --bioprime-ice-white: #F5F7FA;
      --bioprime-dark-blue-black: #020611;
      color-scheme: dark;
    }

    body {
      background-color: var(--bioprime-dark-blue-black);
      color: var(--bioprime-ice-white);
      font-family: 'Inter', system-ui, sans-serif;
      -webkit-font-smoothing: antialiased;
      margin: 0;
      padding: 0;
    }

    .font-display {
      font-family: 'SF Pro Display', system-ui, sans-serif;
    }

    /* Utilitários Tailwind Customizados do tailwind.config.cjs */
    .text-bioprime-iceWhite { color: var(--bioprime-ice-white); }
    .bg-bioprime-darkBlueBlack { background-color: var(--bioprime-dark-blue-black); }
    .bg-bioprime-electricBlue { background-color: var(--bioprime-electric-blue); }
    .text-bioprime-electricBlue { color: var(--bioprime-electric-blue); }
    .text-bioprime-neonGreen { color: var(--bioprime-neon-green); }
    .bg-bioprime-neonGreen { background-color: var(--bioprime-neon-green); }
    
    .border-bioprime-electricBlue\\/40 { border-color: rgba(14, 123, 255, 0.4); }
    .bg-bioprime-electricBlue\\/15 { background-color: rgba(14, 123, 255, 0.15); }
    .bg-bioprime-electricBlue\\/10 { background-color: rgba(14, 123, 255, 0.1); }
    
    .shadow-neon { box-shadow: 0 0 25px rgba(14, 123, 255, 0.35); }
    .shadow-neonGreen { box-shadow: 0 0 25px rgba(57, 255, 90, 0.35); }
    
    .bg-bioprime-radial { 
      background-image: radial-gradient(circle at top, rgba(14,123,255,0.25), transparent 60%), 
                        radial-gradient(circle at bottom, rgba(57,255,90,0.18), transparent 55%); 
    }
    .bg-bioprime-gradient { 
      background-image: linear-gradient(135deg, var(--bioprime-electric-blue) 0%, var(--bioprime-neon-green) 100%); 
    }
    
    .bg-clip-text {
      -webkit-background-clip: text;
      background-clip: text;
    }

    /* Scrollbar moderna */
    ::-webkit-scrollbar { width: 8px; }
    ::-webkit-scrollbar-track { background: #020611; }
    ::-webkit-scrollbar-thumb { background: #0e7bff; border-radius: 9999px; }

    /* Glassmorphism genérico */
    .glass-card {
      background: rgba(5, 11, 31, 0.7);
      border-radius: 1.25rem;
      border: 1px solid rgba(245, 247, 250, 0.06);
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.65);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
    }

    /* Neon border animada */
    .neon-border { position: relative; }
    .neon-border::before {
      content: '';
      position: absolute;
      inset: -1px;
      border-radius: inherit;
      background: linear-gradient(135deg, rgba(14, 123, 255, 0.8), rgba(57, 255, 90, 0.8));
      opacity: 0;
      transition: opacity 0.25s ease-out;
      z-index: -1;
    }
    .neon-border:hover::before { opacity: 1; }

    /* Microinterações de botão */
    .btn-primary {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.75rem 2rem;
      border-radius: 9999px;
      font-size: 0.875rem;
      font-weight: 600;
      letter-spacing: 0.025em;
      background-color: var(--bioprime-electric-blue);
      color: var(--bioprime-ice-white);
      box-shadow: 0 0 25px rgba(14, 123, 255, 0.35);
      transition: transform 0.15s ease-out, box-shadow 0.15s ease-out;
      border: none;
      cursor: pointer;
    }
    @media (min-width: 768px) { .btn-primary { font-size: 1rem; } }
    .btn-primary:hover {
      transform: translateY(-0.125rem);
      box-shadow: 0 0 25px rgba(57, 255, 90, 0.35);
    }

    .btn-ghost {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.75rem 1.75rem;
      border-radius: 9999px;
      font-size: 0.875rem;
      font-weight: 500;
      border: 1px solid rgba(255, 255, 255, 0.15);
      color: rgba(245, 247, 250, 0.8);
      background: transparent;
      transition: all 0.15s ease-out;
      cursor: pointer;
    }
    @media (min-width: 768px) { .btn-ghost { font-size: 1rem; } }
    .btn-ghost:hover {
      color: var(--bioprime-ice-white);
      border-color: rgba(14, 123, 255, 0.7);
      background-color: rgba(255, 255, 255, 0.05);
    }

    /* Animações Substitutas do Framer Motion */
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(26px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .animate-fade-in-up {
      animation: fadeInUp 0.7s ease-out forwards;
    }
    .animate-fade-in-up-delayed {
      animation: fadeInUp 0.9s ease-out 0.15s forwards;
      opacity: 0;
    }
  `}</style>
);

const Hero = () => {
  return (
    <section className="relative pt-24 pb-20 px-6 lg:pt-32 lg:pb-28">
      <div className="max-w-6xl mx-auto grid md:grid-cols-[minmax(0,1.3fr)_minmax(0,1fr)] gap-10 items-center">
        
        {/* Conteúdo textual */}
        <div className="space-y-8 animate-fade-in-up">
          {/* Logo + selo */}
          <div className="flex items-center gap-3">
            <div className="flex items-center gap-2">
              <div className="h-9 w-9 rounded-xl bg-bioprime-electricBlue flex items-center justify-center text-xs font-semibold tracking-wider shadow-neon">
                BP
              </div>
              <span className="font-display text-sm tracking-[0.18em] uppercase text-white/60">
                BioPrime Labs
              </span>
            </div>
            <span className="hidden md:inline-block text-xs px-3 py-1 rounded-full border border-white/15 text-white/60">
              Biotech & Performance Lab
            </span>
          </div>
          
          <div className="space-y-5">
            <h1 className="font-display text-4xl md:text-5xl lg:text-[3.2rem] leading-tight font-semibold text-white">
              Ciência e tecnologia para{' '}
              <span className="bg-clip-text text-transparent bg-bioprime-gradient">
                alta performance.
              </span>
            </h1>
            <p className="text-sm md:text-base text-white/70 max-w-xl leading-relaxed">
              Protocolos avançados, inovação laboratorial e engenharia corporal
              para quem exige outro nível de performance, saúde e estética. Uma
              experiência de biotecnologia premium criada para o corpo do futuro.
            </p>
          </div>

          {/* CTAs */}
          <div className="flex flex-wrap items-center gap-4 pt-2">
            <button className="btn-primary">
              Começar Agora
            </button>
            <button className="btn-ghost">
              Ver protocolos avançados
            </button>
          </div>

          {/* Provas sociais rápidas */}
          <div className="flex flex-wrap items-center gap-6 pt-4 text-xs md:text-sm text-white/60">
            <div className="flex items-center gap-2">
              <span className="h-2 w-2 rounded-full bg-bioprime-neonGreen" />
              <span>Protocolos conduzidos com precisão laboratorial</span>
            </div>
            <div className="hidden md:block h-4 w-px bg-white/15" />
            <div className="flex items-center gap-2">
              <span className="h-6 w-6 rounded-full border border-white/15 flex items-center justify-center text-[0.6rem]">
                AI
              </span>
              <span>Monitoramento inteligente</span>
            </div>
          </div>
        </div>

        {/* Visual Futurista / Biotech */}
        <div className="relative mt-10 md:mt-0 animate-fade-in-up-delayed">
          <div className="glass-card neon-border p-0.5">
            <div className="relative overflow-hidden rounded-[1.15rem] bg-gradient-to-b from-[#050B1F] via-[#030814] to-[#020611]">
              
              {/* Grade e hexágonos abstratos */}
              <div className="absolute inset-0 opacity-30"
                style={{
                  backgroundImage: 'radial-gradient(circle at 1px 1px, rgba(148,163,184,0.3) 1px, transparent 0)',
                  backgroundSize: '32px 32px',
                }}
              />
              <div className="absolute inset-0">
                <svg className="w-full h-full opacity-30" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
                  <defs>
                    <linearGradient id="hex" x1="0" y1="0" x2="1" y2="1">
                      <stop offset="0%" stopColor="#0E7BFF" />
                      <stop offset="100%" stopColor="#39FF5A" />
                    </linearGradient>
                  </defs>
                  <path d="M60 15 L90 32 L90 68 L60 85 L30 68 L30 32 Z" fill="none" stroke="url(#hex)" strokeWidth="1" />
                  <path d="M160 55 L190 72 L190 108 L160 125 L130 108 L130 72 Z" fill="none" stroke="url(#hex)" strokeWidth="1" />
                </svg>
              </div>

              <div className="relative p-6 md:p-7 lg:p-8 space-y-6">
                <div className="flex items-center justify-between gap-4">
                  <div>
                    <p className="text-xs uppercase tracking-[0.22em] text-white/50">
                      Performance Lab
                    </p>
                    <p className="text-lg font-semibold mt-1">
                      BioPrime Neural Protocol
                    </p>
                  </div>
                  <div className="text-right">
                    <p className="text-[0.6rem] uppercase tracking-[0.22em] text-white/50">
                      Status
                    </p>
                    <p className="mt-1 text-xs px-2 py-1 rounded-full bg-bioprime-electricBlue/15 text-bioprime-neonGreen border border-bioprime-electricBlue/40 whitespace-nowrap">
                      Online • 24/7
                    </p>
                  </div>
                </div>

                {/* Indicadores de performance */}
                <div className="grid grid-cols-3 gap-3 text-xs">
                  <div className="glass-card border border-white/5 p-3 rounded-xl bg-gradient-to-b from-white/5 to-transparent">
                    <p className="text-[0.65rem] uppercase tracking-[0.18em] text-white/55">Performance</p>
                    <p className="mt-2 text-xl font-semibold text-bioprime-neonGreen">+142%</p>
                    <p className="mt-1 text-[0.68rem] text-white/60">aumento médio em protocolos</p>
                  </div>
                  <div className="glass-card border border-white/5 p-3 rounded-xl">
                    <p className="text-[0.65rem] uppercase tracking-[0.18em] text-white/55">Recuperação</p>
                    <p className="mt-2 text-xl font-semibold text-bioprime-electricBlue">-38%</p>
                    <p className="mt-1 text-[0.68rem] text-white/60">redução da fadiga sistêmica</p>
                  </div>
                  <div className="glass-card border border-white/5 p-3 rounded-xl">
                    <p className="text-[0.65rem] uppercase tracking-[0.18em] text-white/55">Precisão</p>
                    <p className="mt-2 text-xl font-semibold text-white">99.3%</p>
                    <p className="mt-1 text-[0.68rem] text-white/60">consistência laboratorial</p>
                  </div>
                </div>

                {/* Barra de progresso futurista */}
                <div className="space-y-2 pt-2">
                  <div className="flex justify-between text-[0.68rem] text-white/60">
                    <span>Mapa de evolução corporal</span>
                    <span>Phase 03 • Active</span>
                  </div>
                  <div className="w-full h-2 rounded-full bg-white/5 overflow-hidden">
                    <div className="h-full w-[78%] rounded-full bg-bioprime-gradient shadow-neonGreen" />
                  </div>
                </div>

                {/* CTA secundária */}
                <div className="flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4 pt-1 text-xs">
                  <div className="flex items-center gap-2 text-white/60">
                    <span className="h-6 w-6 rounded-full border border-white/15 flex items-center justify-center shrink-0">
                      <span className="h-2 w-2 rounded-full bg-bioprime-neonGreen" />
                    </span>
                    <span>Monitoramento em tempo real</span>
                  </div>
                  <button className="text-[0.7rem] px-4 py-2 rounded-full border border-bioprime-electricBlue/40 text-bioprime-electricBlue hover:bg-bioprime-electricBlue/10 transition-colors whitespace-nowrap">
                    Ver Dashboard
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  );
};

const Authority = () => (
  <section className="py-10 border-y border-white/5 bg-white/[0.02]">
    <div className="max-w-6xl mx-auto px-6">
      <p className="text-center text-xs uppercase tracking-[0.2em] text-white/40 mb-8">
        Tecnologia validada por atletas e corporações de elite
      </p>
      <div className="flex flex-wrap justify-center gap-8 md:gap-16 opacity-50 grayscale hover:grayscale-0 transition-all duration-500">
        <div className="flex items-center gap-2 font-display text-lg font-bold"><Shield size={24} className="text-bioprime-electricBlue"/> NEUROGUARD</div>
        <div className="flex items-center gap-2 font-display text-lg font-bold"><Activity size={24} className="text-bioprime-neonGreen"/> SYNERGY FIT</div>
        <div className="flex items-center gap-2 font-display text-lg font-bold"><Dna size={24} className="text-bioprime-electricBlue"/> HELIX CORP</div>
        <div className="flex items-center gap-2 font-display text-lg font-bold"><Zap size={24} className="text-white"/> AEX DYNAMICS</div>
      </div>
    </div>
  </section>
);

const About = () => (
  <section className="py-24 px-6 relative">
    <div className="max-w-6xl mx-auto grid md:grid-cols-2 gap-16 items-center">
      <div className="order-2 md:order-1 relative">
         <div className="aspect-square max-w-md mx-auto glass-card border-white/10 p-8 flex flex-col justify-center items-center text-center relative overflow-hidden group">
            <div className="absolute inset-0 bg-bioprime-electricBlue/5 group-hover:bg-bioprime-electricBlue/10 transition-colors duration-500"></div>
            <Microchip size={64} className="text-bioprime-electricBlue mb-6 opacity-80" />
            <h3 className="font-display text-2xl font-semibold mb-3">Engenharia Celular</h3>
            <p className="text-sm text-white/60">Mapeamento genético e otimização metabólica através de inteligência artificial aplicada ao seu biotipo único.</p>
            
            {/* Decoração circular animada */}
            <div className="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-64 h-64 border border-bioprime-electricBlue/20 rounded-full animate-[spin_10s_linear_infinite]" />
            <div className="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-48 h-48 border border-bioprime-neonGreen/10 rounded-full animate-[spin_8s_linear_infinite_reverse]" />
         </div>
      </div>
      <div className="order-1 md:order-2 space-y-6">
        <p className="text-bioprime-electricBlue text-xs font-bold tracking-[0.2em] uppercase">O Laboratório</p>
        <h2 className="font-display text-3xl md:text-4xl font-semibold leading-tight">
          Redefinindo os limites do <br/> corpo humano.
        </h2>
        <p className="text-white/70 leading-relaxed text-sm md:text-base">
          A BioPrime não é apenas uma clínica. É um centro de pesquisa e desenvolvimento focado em uma única missão: extrair o máximo do potencial humano.
        </p>
        <p className="text-white/70 leading-relaxed text-sm md:text-base">
          Nossos protocolos exclusivos combinam nutrologia de precisão, endocrinologia esportiva e biohacking avançado para esculpir físicos perfeitos e mentes afiadas.
        </p>
        <div className="pt-4">
           <button className="flex items-center gap-2 text-sm font-semibold text-bioprime-neonGreen hover:text-white transition-colors group">
             Conheça nossa tecnologia
             <ArrowRight size={16} className="group-hover:translate-x-1 transition-transform" />
           </button>
        </div>
      </div>
    </div>
  </section>
);

const Benefits = () => {
  const cards = [
    { icon: <Target />, title: "Precisão Genética", desc: "Suplementação e treinos baseados no seu DNA. Zero suposições." },
    { icon: <Activity />, title: "Longevidade Ativa", desc: "Protocolos anti-aging que desaceleram o envelhecimento celular." },
    { icon: <Zap />, title: "Hiper-Recuperação", desc: "Terapias intravenosas e modulação para recuperação muscular acelerada." }
  ];

  return (
    <section className="py-24 px-6 bg-[#030814] relative">
      <div className="max-w-6xl mx-auto">
        <div className="text-center mb-16 space-y-4">
          <h2 className="font-display text-3xl md:text-4xl font-semibold">Vantagem Biológica</h2>
          <p className="text-white/50 max-w-xl mx-auto">O que acontece quando você elimina as falhas do sistema e otimiza a máquina.</p>
        </div>
        
        <div className="grid md:grid-cols-3 gap-6">
          {cards.map((card, idx) => (
            <div key={idx} className="glass-card p-8 neon-border transition-all duration-300 hover:-translate-y-2 group">
              <div className="w-12 h-12 rounded-lg bg-bioprime-electricBlue/10 flex items-center justify-center text-bioprime-electricBlue mb-6 group-hover:text-bioprime-neonGreen group-hover:bg-bioprime-neonGreen/10 transition-colors">
                {card.icon}
              </div>
              <h3 className="text-xl font-semibold mb-3">{card.title}</h3>
              <p className="text-sm text-white/60 leading-relaxed">{card.desc}</p>
            </div>
          ))}
        </div>
      </div>
    </section>
  );
};

const Transformation = () => (
  <section className="py-24 px-6 relative overflow-hidden">
    <div className="max-w-4xl mx-auto relative z-10">
      <div className="text-center mb-16">
        <h2 className="font-display text-3xl md:text-4xl font-semibold mb-4">A Jornada BioPrime</h2>
        <p className="text-white/50">Três fases para a sua evolução definitiva.</p>
      </div>

      <div className="space-y-12 relative">
        {/* Linha conectora */}
        <div className="absolute left-8 top-0 bottom-0 w-px bg-gradient-to-b from-bioprime-electricBlue via-bioprime-neonGreen to-transparent hidden md:block"></div>
        
        {[
          { step: "01", title: "Mapeamento Profundo", desc: "Exames de sangue de 120 painéis, análise genômica e escaneamento metabólico para entender seu ponto de partida." },
          { step: "02", title: "Protocolo Algorítmico", desc: "A IA cruza seus dados e nossos especialistas desenham um plano de modulação hormonal, nutricional e física." },
          { step: "03", title: "Evolução e Ajuste", desc: "Monitoramento contínuo 24/7. Ajustes milimétricos baseados na resposta do seu corpo em tempo real." }
        ].map((item, idx) => (
          <div key={idx} className="flex flex-col md:flex-row gap-6 md:gap-12 items-start group">
            <div className="flex items-center justify-center w-16 h-16 rounded-2xl bg-bioprime-darkBlueBlack border border-bioprime-electricBlue/30 text-bioprime-electricBlue font-display text-xl font-bold shadow-neon shrink-0 z-10 group-hover:border-bioprime-neonGreen group-hover:text-bioprime-neonGreen transition-colors">
              {item.step}
            </div>
            <div className="glass-card p-6 md:p-8 flex-1 w-full border-l-2 border-l-bioprime-electricBlue group-hover:border-l-bioprime-neonGreen transition-colors">
              <h3 className="text-xl font-semibold mb-2">{item.title}</h3>
              <p className="text-white/60 text-sm leading-relaxed">{item.desc}</p>
            </div>
          </div>
        ))}
      </div>
    </div>
  </section>
);

const StrongCTA = () => (
  <section className="py-20 px-6">
    <div className="max-w-5xl mx-auto glass-card overflow-hidden relative border-bioprime-electricBlue/30">
      <div className="absolute inset-0 bg-bioprime-gradient opacity-10"></div>
      <div className="absolute top-0 right-0 p-32 bg-bioprime-electricBlue/20 blur-[100px] rounded-full"></div>
      <div className="absolute bottom-0 left-0 p-32 bg-bioprime-neonGreen/10 blur-[100px] rounded-full"></div>
      
      <div className="relative z-10 px-8 py-16 md:py-20 text-center flex flex-col items-center">
        <Beaker size={48} className="text-bioprime-electricBlue mb-6" />
        <h2 className="font-display text-3xl md:text-5xl font-bold mb-6 max-w-2xl">
          Pronto para fazer o <br className="hidden md:block"/> upload da sua performance?
        </h2>
        <p className="text-white/70 mb-10 max-w-lg">
          Vagas limitadas para novos protocolos neste trimestre. Agende sua consultoria de viabilidade.
        </p>
        <button className="btn-primary flex items-center gap-2 group text-lg px-10 py-4">
          Iniciar Aplicação
          <ChevronRight size={20} className="group-hover:translate-x-1 transition-transform" />
        </button>
      </div>
    </div>
  </section>
);

const Footer = () => (
  <footer className="border-t border-white/5 py-12 px-6 mt-12 bg-black/20">
    <div className="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
      <div className="flex items-center gap-2">
        <div className="h-6 w-6 rounded bg-bioprime-electricBlue flex items-center justify-center text-[0.5rem] font-bold">BP</div>
        <span className="font-display text-sm tracking-widest uppercase text-white/50">BioPrime Labs</span>
      </div>
      <div className="flex gap-6 text-xs text-white/40">
        <a href="#" className="hover:text-white transition-colors">Termos de Serviço</a>
        <a href="#" className="hover:text-white transition-colors">Política de Privacidade</a>
        <a href="#" className="hover:text-white transition-colors">Contato Lab</a>
      </div>
      <div className="text-xs text-white/30">
        © 2026 BioPrime Labs. All systems operational.
      </div>
    </div>
  </footer>
);

function App() {
  const [mounted, setMounted] = useState(false);

  useEffect(() => {
    setMounted(true);
  }, []);

  if (!mounted) return null;

  return (
    <>
      <GlobalStyles />
      <div className="min-h-screen relative overflow-hidden bg-bioprime-darkBlueBlack text-bioprime-iceWhite">
        
        {/* Glow de fundo global */}
        <div className="pointer-events-none fixed inset-0 bg-bioprime-radial opacity-80 mix-blend-screen" />

        {/* Grade sutil futurista */}
        <div className="pointer-events-none fixed inset-0 opacity-[0.05]"
          style={{
            backgroundImage: 'linear-gradient(to right, #ffffff 1px, transparent 1px), linear-gradient(to bottom, #ffffff 1px, transparent 1px)',
            backgroundSize: '72px 72px',
          }}
        />

        {/* Conteúdo Principal */}
        <main className="relative z-10 selection:bg-bioprime-electricBlue selection:text-white">
          <Hero />
          <Authority />
          <About />
          <Benefits />
          <Transformation />
          <StrongCTA />
          <Footer />
        </main>
      </div>
    </>
  );
}

export default App;
