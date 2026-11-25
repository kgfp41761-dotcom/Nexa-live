# Voice Rooms Live

LiveKit पर चलने वाला वॉइस रूम ऐप। पब्लिक/प्राइवेट रूम, "सिर्फ सुनना" मोड, म्यूट और स्पीकिंग इंडिकेटर।

## सेटअप (एक बार)

1. https://cloud.livekit.io पर मुफ्त अकाउंट बनाओ और एक प्रोजेक्ट बनाओ।
   Settings → Keys से ये तीन चीज़ें कॉपी करो:
   - WebSocket URL (जैसे `wss://xxxx.livekit.cloud`)
   - API Key
   - API Secret
2. इस फोल्डर को GitHub पर डालो और https://app.netlify.com पर "Import from Git" से जोड़ो।
   (ध्यान दो: सिर्फ index.html ड्रैग करने से काम नहीं चलेगा, क्योंकि `netlify/functions` भी चाहिए।)
3. Netlify में Site settings → Environment variables में ये तीन जोड़ो:
   - `LIVEKIT_URL`
   - `LIVEKIT_API_KEY`
   - `LIVEKIT_API_SECRET`
4. Deploy दोबारा चलाओ। बस, लिंक खोलकर रूम बनाओ।

## फाइलें

- `index.html`: ऐप का पूरा इंटरफेस
- `netlify/functions/token.js`: जुड़ने का टोकन देता है (Secret यहीं सुरक्षित रहता है)
- `netlify/functions/rooms.js`: पब्लिक रूम की लिस्ट देता है

## ध्यान रखो

- API Secret कभी `index.html` में मत डालो।
- LiveKit का मुफ्त प्लान सीमित है। ज़्यादा लोग आएँ तो प्लान देखना पड़ेगा।
- कोई भी पब्लिक रूम बना सकता है। असली दुनिया में चलाने से पहले रिपोर्ट/ब्लॉक जैसी मॉडरेशन सुविधा सोचो।
