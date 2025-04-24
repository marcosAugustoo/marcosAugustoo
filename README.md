import { useEffect, useState } from "react";
import { motion } from "framer-motion";

export default function SobreMim() {
  const frases = [
    "Motoboy por necessidade 🚴",
    "Desenvolvedor por vocação 💻",
    "Futuro dev na FURIA 🔥"
  ];

  const [fraseIndex, setFraseIndex] = useState(0);

  useEffect(() => {
    const intervalo = setInterval(() => {
      setFraseIndex((prev) => (prev + 1) % frases.length);
    }, 3000);
    return () => clearInterval(intervalo);
  }, []);

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 to-black text-white p-6 flex flex-col items-center justify-center gap-6">
      <motion.img
        src="https://media.giphy.com/media/XUFPGrX5Zis6Y/giphy.gif"
        alt="Motoboy to Dev"
        className="rounded-2xl w-80 shadow-lg"
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ duration: 1 }}
      />

      <motion.h1
        className="text-4xl font-bold text-center"
        initial={{ y: -20, opacity: 0 }}
        animate={{ y: 0, opacity: 1 }}
        transition={{ duration: 1 }}
      >
        Olá, sou Marcos 👋
      </motion.h1>

      <motion.p
        className="text-xl text-center max-w-xl"
        key={fraseIndex}
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ duration: 0.6 }}
      >
        {frases[fraseIndex]}
      </motion.p>

      <div className="grid gap-4 mt-6 max-w-2xl text-center">
        <p>
          Estudo <strong>SI no Eniac</strong>, aprendendo tecnologias como <strong>Python</strong>, <strong>JavaScript</strong>, <strong>React</strong>, <strong>Next.js</strong> e <strong>Node.js</strong> de forma autodidata.
        </p>
        <p>
          Fã de <strong>eSports</strong> e dos vídeos do <strong>bronziocre</strong>. Acompanho <strong>LoL</strong> e admiro a <strong>FURIA</strong> como referência em tecnologia e impacto no cenário gamer.
        </p>
        <p>
          Fora do teclado? Sou líbero no vôlei amador 🏐 e apaixonado por aprender e crescer 💪
        </p>
      </div>

      <motion.img
        src="https://media.giphy.com/media/iOeu9XEUCosKUN0b4r/giphy.gif"
        alt="LOL gif"
        className="w-64 rounded-xl shadow"
        initial={{ scale: 0 }}
        animate={{ scale: 1 }}
        transition={{ duration: 1 }}
      />

      <footer className="mt-10 text-sm text-gray-400">
        "Você não precisa ser grande para começar, mas precisa começar para ser grande."
      </footer>
    </div>
  );
}
