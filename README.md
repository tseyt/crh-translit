# **Qırımtatar Script Converter (crh-translit)**

A fast, privacy-focused, bidirectional transliteration tool for the Crimean Tatar language. This tool converts text between the Cyrillic script (Soviet era) and the modern Latin script (2012/Official standard) entirely in the browser.

[**Live Demo**](https://tseyt.github.io/crh-translit)

## **🚀 Features**

* **Bi-directional Conversion:** Instantly switch between Cyrillic → Latin and Latin → Cyrillic.  
* **Smart Digraphs:** Automatically handles multi-character phonemes like гъ (ğ), къ (q), нъ (ñ), and дж (c).  
* **Context-Aware Logic:**  
  * Handles contextual vowels: е → ye (initial) vs e (medial).  
  * Softness rules: ля → lâ, кя → kâ.  
* **Large File Support:** Capable of processing .txt files up to \~5MB (approx. a 500-page book) using a debounced input stream to prevent UI freezing.  
* **Privacy First:** No server-side processing. All text conversion happens locally in the user's browser using JavaScript.

## **🛠 Technical Details**

This project uses a deterministic state machine approach for transliteration rather than simple character replacement.

### **The "Digraph-First" Priority**

The converter prioritizes digraphs before single characters to prevent collision.

* *Input:* гъалебе  
* *Logic:* It detects гъ before г.  
* *Output:* ğalebe (Correct) instead of g \+ ъ \+ alebe.

### **Soft Vowel Heuristics**

Cyrillic often uses one character to represent two sounds (yotated vowels) or softness. The Latin script is explicit.

* **Initial Position:** Я → Ya (e.g., Ярым → Yarım)  
* **Post-Consonant:** Я → Â (e.g., Аля → Alâ)

## **📦 Installation & Usage**

Since this is a static web application, you don't need npm or a build step.

1. **Clone the repo**  
   git clone [https://github.com/tseyt/crh-translit.git](https://github.com/tseyt/crh-translit.git)

2. **Run locally**  
   * Open index.html in any web browser.  
   * Or use a simple HTTP server:  
     python3 \-m http.server

## **🤝 Contributing**

Contributions are welcome\! This tool aims to help standardizing the Crimean Tatar Latin script adoption.

1. Fork the project.  
2. Create your feature branch (git checkout \-b feature/AmazingFeature).  
3. Commit your changes (git commit \-m 'Add some AmazingFeature').  
4. Push to the branch (git push origin feature/AmazingFeature).  
5. Open a Pull Request.

## **📝 License**

Distributed under the MIT License. See LICENSE for more information.

*Made with ❤️ for Vatan Qırım.*
