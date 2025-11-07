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

````md
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
````

---

#### 🧩 Your Example (Extended & Practical)

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

```
```
