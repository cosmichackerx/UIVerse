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
---

## 📦 Concept: LinearLayout — Vertical & Horizontal Composition

---

## 🔤 Definitions (briefly for clarity)
**LinearLayout** is a ViewGroup that arranges its children in a **single row or column** — either *vertically* or *horizontally*.  
It’s one of the most used containers in Android UI design, perfect for simple, linear, and predictable layouts.

**Views** inside it (like TextView, ImageView, Button, EditText) can be sized, aligned, and spaced using layout parameters such as:
- `layout_width`, `layout_height`
- `orientation`
- `layout_weight`
- `gravity`, `layout_gravity`
- `padding`, `margin`

---

### 1️⃣ Concept Overview
`LinearLayout` arranges all its child elements **sequentially** in either:
- **Vertical** direction → like a scroll of stacked items (e.g., Instagram feed posts)
- **Horizontal** direction → like button bars or chat bubbles side by side.

Think of it like arranging *blocks in a straight line* — either top-to-bottom or left-to-right.

---

### 2️⃣ Core Properties (Must-Mention Parameters)

| Property | Description | Example |
|-----------|--------------|----------|
| `android:orientation` | Defines the direction — vertical or horizontal | `"vertical"` / `"horizontal"` |
| `android:layout_weight` | Distributes available space proportionally | `layout_weight="1"` |
| `android:gravity` | Controls internal alignment (inside parent) | `"center"`, `"end"`, `"top"` |
| `android:layout_gravity` | Aligns child inside parent container | `"center_horizontal"` |
| `android:baselineAligned` | Aligns text baselines for readability | `"true"` |
| `android:divider` & `android:showDividers` | Adds visual separation between children | `"middle"` |

---

### 3️⃣ 🧠 Mnemonics & Analogies

| English Mnemonic | Urdu Analogy (اردو تشبیہ) | Meaning |
|------------------|-----------------------------|----------|
| **L for Line** → *LinearLayout = Line Layout* | **قطار میں بیٹھے دوستوں کی طرح** | Everything in one straight line |
| **Weight = Space Share** | **سب کو برابر کرسی دینا** | Divides space equally among children |
| **Gravity = Pull** | **کشش کی سمت** | Where the child is pulled or aligned |
| **Orientation = Direction** | **سمت یا رخ** | Defines if layout goes vertically or horizontally |

---

### 4️⃣ 💻 Code Snippet (Minimal + Practical)

**Example Source:** Inspired by **Instagram’s post card** (profile → text → buttons → comment input)

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

    <!-- Header -->
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

    <!-- Horizontal row with image + text -->
    <LinearLayout
        android:id="@+id/horizontal_row"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginVertical="12dp">

        <ImageView
            android:id="@+id/avatar"
            android:layout_width="0dp"
            android:layout_height="80dp"
            android:layout_weight="1"
            android:src="@mipmap/ic_launcher"
            android:scaleType="centerCrop"
            android:contentDescription="avatar" />

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

    <!-- Button row -->
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
            android:layout_marginHorizontal="8dp" />

        <Button
            android:id="@+id/btn_share"
            android:layout_width="0dp"
            android:layout_height="48dp"
            android:layout_weight="1"
            android:text="Share" />
    </LinearLayout>

    <!-- Form section -->
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
