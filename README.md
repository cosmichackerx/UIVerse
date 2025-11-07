# UIVerse
> A complete roadmap of Android UI layouts and views — from beginner to pro, XML to Jetpack Compose.
---
## 🌱 **BEGINNER LEVEL — Foundation of Android Layouts**
1. **LinearLayout**
2. **RelativeLayout**
3. **FrameLayout**
4. **TableLayout**
5. **ScrollView**
6. **NestedScrollView**
7. **Space**
---

---

## 📐 Concept: LinearLayout — Organizing Views Vertically & Horizontally

## 🔤 Definition
**LinearLayout** arranges its child views **in a single direction — either vertically or horizontally.**  
It’s one of the simplest and most commonly used layouts in Android for stacking elements in order.  

---

### 1️⃣ Concept Overview
LinearLayout helps you align elements **one after another**, making it ideal for lists, toolbars, or form screens.  
You can use:
- `android:orientation="vertical"` → items stacked top to bottom  
- `android:orientation="horizontal"` → items placed left to right  

When combined with **weights**, LinearLayout can **proportionally distribute space** among its children.

---

### 2️⃣ Core Properties (Must-Mention Parameters)

| Property | Description |
|-----------|--------------|
| `android:orientation` | Direction of arrangement (`vertical` or `horizontal`) |
| `android:weightSum` | Total weight used for distributing available space |
| `android:layout_weight` | Defines how much space each child should take relative to others |
| `android:gravity` | Aligns children within the layout (center, start, end, etc.) |
| `android:divider` | Adds visual dividers between elements |
| `android:baselineAligned` | Ensures text baselines align (useful for text-heavy UIs) |

---

### 3️⃣ 🧠 Mnemonics & Analogies (English + Urdu)

| Mnemonic / Analogy | English Meaning | Urdu Translation |
|---------------------|------------------|------------------|
| “Line = One Direction” | Everything flows in one straight line | “LineLayout har cheez ko aik line mein rakhta hai.” |
| “Weight = Share Space” | Divide layout space like slices of pizza | “Weight ka matlab hai har view ko uska hissa milta hai.” |
| “Orientation = Path” | Vertical or Horizontal defines the direction of flow | “Orientation tay karti hai ke views upar se niche ya daayn se baayn jayenge.” |

---

### 4️⃣ 💻 Code Snippet (Minimal + Practical)

#### Example inspired by **Instagram Post Layout**
A simplified example showing an image, text, and buttons arranged using LinearLayout.

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="12dp">

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:src="@drawable/sample_photo"
        android:scaleType="centerCrop" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Beautiful sunset vibes 🌅"
        android:textSize="16sp"
        android:layout_marginTop="8dp" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginTop="8dp">

        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Like" />

        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Comment" />
    </LinearLayout>
</LinearLayout>
```
---

#### 🧩 our Example (Extended & Practical)

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- res/layout/activity_linear_example.xml -->
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/root_linear"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:background="#FFFFFF"
    android:divider="?android:attr/dividerHorizontal"
    android:showDividers="middle"
    android:baselineAligned="true">

    <TextView
        android:id="@+id/header"
        android:layout_width="match_parent"
        android:layout_height="56dp"
        android:gravity="center_vertical"
        android:text="LinearLayout Demo"
        android:textSize="20sp"
        android:textStyle="bold"
        android:paddingStart="8dp"
        android:paddingEnd="8dp" />

    <LinearLayout
        android:id="@+id/horizontal_row"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginTop="12dp"
        android:layout_marginBottom="12dp">

        <ImageView
            android:id="@+id/avatar"
            android:layout_width="0dp"
            android:layout_height="80dp"
            android:layout_weight="1"
            android:src="@mipmap/ic_launcher"
            android:contentDescription="avatar"
            android:scaleType="centerCrop" />

        <LinearLayout
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="2"
            android:orientation="vertical"
            android:paddingStart="12dp"
            android:gravity="center_vertical">

            <TextView
                android:id="@+id/title"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Title goes here"
                android:textSize="16sp"
                android:textStyle="bold" />

            <TextView
                android:id="@+id/subtitle"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Subtitle or description"
                android:textSize="14sp"
                android:layout_marginTop="4dp" />
        </LinearLayout>
    </LinearLayout>

    <LinearLayout
        android:id="@+id/button_row"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:weightSum="3"
        android:layout_marginBottom="12dp">

        <Button
            android:id="@+id/btn_like"
            android:layout_width="0dp"
            android:layout_height="48dp"
            android:layout_weight="1"
            android:text="Like" />

        <Button
            android:id="@+id/btn_comment"
            android:layout_width="0dp"
            android:layout_height="48dp"
            android:layout_weight="1"
            android:text="Comment"
            android:layout_marginStart="8dp"
            android:layout_marginEnd="8dp" />

        <Button
            android:id="@+id/btn_share"
            android:layout_width="0dp"
            android:layout_height="48dp"
            android:layout_weight="1"
            android:text="Share" />
    </LinearLayout>

    <EditText
        android:id="@+id/input_name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Your name"
        android:inputType="textPersonName"
        android:layout_marginBottom="8dp" />

    <EditText
        android:id="@+id/input_message"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Message"
        android:inputType="textMultiLine"
        android:minLines="3"
        android:gravity="top"
        android:layout_marginBottom="12dp" />

    <View
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1" />

    <TextView
        android:id="@+id/footer"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:gravity="center"
        android:text="Made with ❤️ using LinearLayout"
        android:textSize="14sp" />

</LinearLayout>
```

---

### 5️⃣ Real-World Analogy / App Reference

📱 **Example App:** *Instagram & WhatsApp Chat Screens*
LinearLayout is used to stack message bubbles, captions, or comments vertically.
Think of it like **a column of posts or chat messages**, one after another — clean, simple, organized.

---

### 6️⃣ Common Mistakes / Gotchas

| Mistake                                   | Description                             | Fix                                                 |
| ----------------------------------------- | --------------------------------------- | --------------------------------------------------- |
| ❌ Mixing nested LinearLayouts             | Leads to performance issues             | ✅ Use ConstraintLayout or RelativeLayout if complex |
| ❌ Forgetting weights in horizontal layout | Elements might not share space properly | ✅ Add `layout_weight` with `width=0dp`              |
| ❌ Large nested hierarchy                  | Slows down UI rendering                 | ✅ Flatten layout when possible                      |
| ❌ Ignoring `baselineAligned="false"`      | Text alignment may look off             | ✅ Set baselineAligned false for mixed content rows  |

---

---

## 🔤 Definition (RelativeLayout)
**RelativeLayout** is a ViewGroup in Android that allows you to **position child views relative to each other or to the parent container**.  
It gives flexibility to create dynamic layouts — e.g., align one view to another’s bottom, right, or center — without strict linear order.

---

## 📱 Code Example Reference (Based on Popular App)
**App Reference:** Instagram’s profile screen layout — the “Edit Profile” button and user stats are aligned **relative to each other**, similar to how RelativeLayout positions elements.

---

### 1️⃣ Concept Overview
- **RelativeLayout** helps you align UI components **based on relationships** — like “below,” “toRightOf,” “centerInParent,” etc.
- Perfect for **non-linear UI arrangements** (e.g., overlapping elements, custom positioning).

---

### 2️⃣ Core Properties (Must-Mention Parameters)
| Property | Description |
|-----------|--------------|
| `android:layout_below` | Positions a view **below** another view. |
| `android:layout_above` | Positions a view **above** another view. |
| `android:layout_toEndOf` / `layout_toRightOf` | Places a view **to the right** of another. |
| `android:layout_alignParentStart` / `alignParentEnd` | Aligns view edges to **parent’s sides**. |
| `android:layout_centerHorizontal` / `centerVertical` | Centers a view horizontally or vertically. |
| `android:layout_alignBaseline` | Aligns text baselines between two views. |

---

### 3️⃣ 🧠 Mnemonics & Analogies (English + Urdu)
| Mnemonic | English Meaning | Urdu Meaning |
|-----------|----------------|---------------|
| **“RELATE to place”** | Think of “Relative” as positioning things **in relation** to others. | "RelativeLayout میں views ایک دوسرے سے **تعلق کی بنیاد پر** رکھے جاتے ہیں۔" |
| **“Center or Side?”** | Either center things or attach to parent sides. | "یا تو center کرو یا parent کے کنارے سے جوڑو۔" |
| **“Below to flow”** | If you want something below another — use `layout_below`. | "کسی چیز کو نیچے رکھنا ہے؟ `layout_below` لگاؤ!" |

---

### 4️⃣ 💻 Code Snippet (Minimal + Practical)
Here’s a simple **RelativeLayout** combining these ideas —  
💡 **(based on the Instagram login screen pattern)**

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="20dp"
    android:background="#121212">

    <!-- Title TextView at the top center -->
    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Relative Layout Demo"
        android:textColor="#FFFFFF"
        android:textSize="20sp"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="30dp" />

    <!-- Image below the title -->
    <ImageView
        android:id="@+id/demoImage"
        android:layout_width="120dp"
        android:layout_height="120dp"
        android:src="@mipmap/ic_launcher"
        android:layout_below="@id/titleText"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="20dp" />

    <!-- Username label aligned to the left -->
    <TextView
        android:id="@+id/usernameLabel"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Username:"
        android:textColor="#BB86FC"
        android:textSize="16sp"
        android:layout_below="@id/demoImage"
        android:layout_alignParentStart="true"
        android:layout_marginTop="40dp" />

    <!-- Username input aligned to the right of label -->
    <EditText
        android:id="@+id/usernameInput"
        android:layout_width="200dp"
        android:layout_height="wrap_content"
        android:hint="Enter username"
        android:textColorHint="#AAAAAA"
        android:textColor="#FFFFFF"
        android:backgroundTint="#BB86FC"
        android:layout_toEndOf="@id/usernameLabel"
        android:layout_alignBaseline="@id/usernameLabel"
        android:layout_marginStart="10dp" />

    <!-- Login button centered below username -->
    <Button
        android:id="@+id/loginButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Login"
        android:textColor="#FFFFFF"
        android:backgroundTint="#6200EE"
        android:layout_below="@id/usernameInput"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="30dp" />

</RelativeLayout>
```

---

### 5️⃣ Real-World Analogy / App Reference

Think of **RelativeLayout** like placing furniture in a room:

* “Put the lamp **to the right of** the sofa.”
* “Keep the rug **below** the table.”
  That’s exactly how **RelativeLayout** arranges its children.

📲 Used in **Instagram**, **LinkedIn**, and **Google Play Store** headers to align icons/text side-by-side relative to each other.

---

### 6️⃣ Common Mistakes / Gotchas

| Mistake                           | Why It Happens                                                   | Fix                                           |
| --------------------------------- | ---------------------------------------------------------------- | --------------------------------------------- |
| Missing ID in referenced view     | `layout_below="@id/someView"` fails if `someView` has no ID.     | Always assign IDs before referencing.         |
| Overlapping views unintentionally | Conflicting constraints (e.g., both `centerInParent` + `below`). | Use only one major positioning rule per axis. |
| Hardcoding sizes                  | Breaks responsiveness on different screens.                      | Use `wrap_content` / `match_parent` wisely.   |
| Mixing too many rules             | Creates layout confusion.                                        | Keep relationships simple and logical.        |

---

---

## 🔤 Definition (FrameLayout)
**FrameLayout** is a simple layout designed to block out an area on the screen to display a single item at a time. However, you can place multiple child views inside it — each new child view will be drawn **on top** of the previous one (like stacking layers). It’s ideal for overlaying content, image backgrounds, or floating UI elements (e.g., like profile icons over a cover photo).

---

## 💻 Code Example (Based on a Popular App)
This layout concept is inspired by **Spotify's Player Screen**, where album art serves as the background, and controls or overlays appear on top.

---

### 1️⃣ Concept Overview
FrameLayout behaves like a **stack of views** — the first child is at the back, and the last one sits at the top. It’s excellent for overlapping UI components such as:
- Background images
- Floating buttons
- Loading overlays
- Banners or notifications over content

---

### 2️⃣ Core Properties (Must-Mention Parameters)

| Property | Description |
|-----------|--------------|
| `android:layout_gravity` | Positions child views inside the FrameLayout (e.g., `center`, `bottom|end`). |
| `android:foreground` | Draws a drawable or color overlay over all children (e.g., for dimming effects). |
| `android:foregroundGravity` | Aligns the foreground drawable. |
| `android:measureAllChildren` | If `true`, all children are measured even if `GONE`. Useful for animations or transitions. |
| `android:padding` | Controls inner spacing. Often used for uniform visual balance. |

---

### 3️⃣ 🧠 Mnemonics & Analogies (English + Urdu)

| Mnemonic | Meaning (English) | مطلب (Urdu) |
|-----------|------------------|--------------|
| **F → Floating Layers** | Think of FrameLayout as floating image layers stacked up. | **فریم لے آؤٹ** کو فلوٹنگ لیئرز سمجھیں، ایک دوسرے کے اوپر چڑھی ہوئی۔ |
| **R → Rear to Front Rule** | First view goes behind, last view comes in front. | پہلا ویو پیچھے، آخری ویو سب سے آگے۔ |
| **A → Always Overlay** | Designed to overlap and layer content easily. | اوورلیپ کے لیے بنایا گیا ہے۔ |

---

### 4️⃣ Code Snippet (Minimal + Practical)  
💻 Includes our provided example too 👇

```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#121212"
    android:padding="16dp">

    <!-- Background Image (lowest layer) -->
    <ImageView
        android:id="@+id/backgroundImage"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:scaleType="centerCrop"
        android:src="@drawable/sample_bg"
        android:alpha="0.4" />

    <!-- Centered Text (above background) -->
    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="FrameLayout Example"
        android:textSize="22sp"
        android:textStyle="bold"
        android:textColor="#FFFFFF"
        android:layout_gravity="center" />

    <!-- Floating Button (top-right corner) -->
    <Button
        android:id="@+id/fabButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="➕"
        android:textSize="18sp"
        android:backgroundTint="#BB86FC"
        android:textColor="#FFFFFF"
        android:layout_gravity="top|end"
        android:layout_margin="16dp" />

    <!-- Overlay Box (bottom area) -->
    <TextView
        android:id="@+id/footerText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Overlay Content Layer"
        android:textSize="16sp"
        android:textColor="#FFFFFF"
        android:background="#66000000"
        android:padding="12dp"
        android:layout_gravity="bottom" />

</FrameLayout>
```

---

### 5️⃣ Real-World Analogy / App Reference

Imagine **Spotify’s Now Playing Screen**:

* Album art in the background (first child)
* Song title + controls in the middle
* Floating play button on top
  That’s **FrameLayout** — layers on layers!

---

### 6️⃣ Common Mistakes / Gotchas

| Mistake                     | Why It Happens                                   | Fix                                           |
| --------------------------- | ------------------------------------------------ | --------------------------------------------- |
| Overlapping unintentionally | Adding multiple children without layout gravity. | Use `android:layout_gravity` properly.        |
| Misaligned buttons          | Forgetting to set gravity or margin.             | Combine `layout_gravity` and `layout_margin`. |
| Hidden views                | Later views overlap earlier ones fully.          | Adjust size or transparency (`alpha`).        |
| Ignoring performance        | Too many overlays slow rendering.                | Keep child count minimal.                     |

---

