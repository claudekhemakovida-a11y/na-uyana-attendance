# නා උයන ධර්මායතනය — සේවක පැමිණීමේ ලේඛනය

Nā Uyana Dharmāyatanaya — staff attendance register. GitHub Pages මත ක්‍රියා කරන, දුරකථනයට ස්ථාපනය කළ හැකි (PWA) වෙබ් ඇප් එකකි. දත්ත ගබඩාව සහ පිවිසුම Google Firebase (නොමිලේ "Spark" සැලැස්ම) හරහා සිදු වේ.

## ඇප් එක සකසන ආකාරය (එක් වරක් පමණි)

### 1. Firebase ව්‍යාපෘතිය
1. <https://console.firebase.google.com> → **Create a project** → නම: `na-uyana-attendance` (Google Analytics අවශ්‍ය නැත).
2. **Build → Authentication → Get started → Sign-in method → Google → Enable → Save**.
3. **Authentication → Settings → Authorized domains → Add domain** → `claudekhemakovida-a11y.github.io`
4. **Build → Firestore Database → Create database** → ස්ථානය `asia-south1` → **production mode**.
5. **Firestore Database → Rules** → මෙම repository හි ඇති `firestore.rules` ගොනුවේ අන්තර්ගතය සම්පූර්ණයෙන් පිටපත් කර අලවා **Publish** ඔබන්න.
6. **Project settings (⚙️) → General → Your apps → `</>`** → නම `attendance` → ලැබෙන `firebaseConfig` අගයන් `config.js` ගොනුවේ `window.FIREBASE_CONFIG = { ... };` ලෙස ඇතුළත් කරන්න.

### 2. පළමු පරිපාලක
- ඇප් එක විවෘත කර ඔබේ Google ගිණුමෙන් පිවිසෙන්න.
- "පළමු පරිපාලක සැකසුම" තිරයේ **මම පරිපාලක ලෙස ලියාපදිංචි වෙමි** ඔබන්න. (මෙය කළ හැක්කේ පළමු පුද්ගලයාට පමණි. එම නිසා ඇප් එක සකසූ වහාම මෙය කරන්න.)
- **සැකසුම් → පරිපාලකයින්** යටතේ දෙවන පරිපාලකයාගේ Google email ලිපිනය එක් කරන්න.

### 3. සේවකයින් සහ QR කේතය
- **සේවකයින්** ටැබයේ සේවකයින් එක් කරන්න (හෝ "පෙර ලේඛනයේ නම් 3 එක් කරන්න" ඔබන්න).
- **QR කේතය** ටැබයෙන් QR රූපය බාගෙන, මුද්‍රණය කර කාර්යාල දොරටුව අසල අලවන්න.
- සේවකයා QR ස්කෑන් කර Google ගිණුමෙන් පිවිස, තම නම තෝරයි. පරිපාලක **සේවකයින්** ටැබයේ එය අනුමත කරයි.

### 4. දුරකථනයට ස්ථාපනය
- **Android (Chrome):** ඇප් එකේ ඉහළ ඇති **ඇප් එක ස්ථාපනය කරන්න** බොත්තම, නැතහොත් ⋮ → **Install app / Add to Home screen**.
- **iPhone (Safari):** Share → **Add to Home Screen**.

## ගොනු
| ගොනුව | කාර්යය |
|---|---|
| `index.html` | ඇප් එක (සිංහල / English, ලා අළු / ලා කළු තේමා) |
| `config.js` | Firebase සැකසුම් |
| `firestore.rules` | දත්ත ආරක්ෂක නීති (Firebase console හි Publish කළ යුතුය) |
| `manifest.webmanifest`, `sw.js`, `icons/` | දුරකථනයට ස්ථාපනය කිරීමට |
| `logo-light.webp`, `logo-dark.webp` | ලෝගෝව |

## ආරක්ෂාව
- `config.js` හි ඇති Firebase අගයන් රහස් නොවේ. දත්ත ආරක්ෂා කරන්නේ `firestore.rules` මගිනි.
- සේවකයාට ලිවිය හැක්කේ තමාගේ පැමිණීම් පමණි. ජාතික හැඳුනුම්පත, දුරකථනය, ලිපිනය වැනි විස්තර කියවිය හැක්කේ පරිපාලකයින්ට පමණි.
- Google ගිණුමක් ඇති ඕනෑම අයෙකුට සේවක නම් ලැයිස්තුව දැකිය හැක (නම තේරීමට එය අවශ්‍යයි). ඔහුගේ ලියාපදිංචිය පරිපාලක අනුමත කරන තුරු ලේඛනයේ පෙන්වන්නේ නැත.
