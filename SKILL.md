---
name: travel-itinerary-planner
description: Use this skill when the user asks to plan a trip, build a travel itinerary, organize daily schedules, optimize a tourist pass, generate an HTML travel page, or create an interactive travel map. It guides the assistant to research destinations, cluster attractions efficiently, account for opening hours and transit time, and produce structured outputs in Traditional Chinese including day-by-day itineraries, HTML visual pages, and multi-day maps.
---

# Travel Itinerary Planner Skill

## Purpose

This skill helps produce a reliable, repeatable **旅遊行程規劃** workflow. Use it when the task involves trip planning, destination research, sightseeing schedules, transportation routing, tourist pass optimization, accommodation area selection, or travel output generation (HTML itinerary pages, interactive maps, day-by-day tables).

Default output language: **繁體中文**

Default audience: self-planned travelers who prefer detailed, hands-on itineraries with clear timing, transit notes, and practical tips — not generic tour packages.

---

## Core Principles

1. **Cluster by geography.** Group attractions by proximity to minimize transit time. Never schedule a morning spot in the north and an afternoon spot in the south unless there's a strong reason.
2. **Respect opening hours and peak times.** Always verify operating hours. Schedule crowded attractions early morning or late afternoon to avoid queues.
3. **Optimize pass usage.** When a tourist pass (e.g., city pass, transport card) is involved, identify which paid attractions are covered and cluster them within the pass validity window to maximize value.
4. **Build in buffer time.** Add 15–30 minutes between each stop for transit, rest, and unexpected delays. Meals should be allocated 60–90 minutes.
5. **Prioritize must-dos first.** Ask or infer the traveler's top priorities. Lock those in first, then fill remaining time with secondary spots.
6. **Adapt to weather and season.** Note if certain activities are weather-dependent (outdoor markets, beach areas, rooftop cafés) and suggest indoor backups.
7. **Separate walking and transit legs clearly.** Specify whether movement between stops is on foot, by subway, bus, taxi, or other means, with estimated travel time.

---

## Standard Workflow

### 1. Clarify trip parameters (if not provided)

Collect or infer:
- Destination city / region
- Travel dates and number of days
- Accommodation area (affects daily routing)
- Number of travelers and composition (solo, couple, family, group)
- Travel style: relaxed vs. packed, culture vs. food vs. nature vs. shopping
- Budget level: budget / mid-range / luxury
- Any tourist pass or transport card being used
- Must-visit spots or hard constraints (e.g., a specific restaurant reservation)

### 2. Research and gather destination data

For each destination, collect:
- **Top attractions** with addresses, opening hours, entrance fees, recommended visit duration
- **Local food spots** (breakfast, lunch, dinner, night market, café)
- **Transport options**: subway lines, bus routes, walking distances, taxi/ride-hail availability
- **Accommodation area characteristics**: walkability, nightlife, transit access
- **Seasonal notes**: weather, festivals, events during travel dates
- **Tourist pass coverage**: which sites are included, activation rules, expiry logic

Preferred sources:
- Official tourism boards (e.g., 釜山觀光公社、台灣觀光局)
- Google Maps for transit times and business hours
- TripAdvisor, Klook, KKday for pass and attraction details
- Local travel blogs and community forums (PTT, Dcard, 背包客棧) for insider tips

### 3. Build a daily logistics table

Before writing the itinerary narrative, create an internal planning table:

| Time | Stop | Category | Duration | Transit to next | Notes |
|------|------|----------|----------|-----------------|-------|
| 09:00 | 광안리 해수욕장 | 景點 | 60 min | 步行 10 min | 早晨人少，適合拍照 |

Use this table to catch scheduling conflicts, unrealistic transit times, or gaps.

### 4. Optimize tourist pass day (if applicable)

If the traveler holds a tourist pass:
- List all covered attractions/services with individual market value
- Select the highest-value combination that fits geographically on one day
- Calculate total savings vs. pass cost
- Note activation timing (activate at first use, not purchase)

### 5. Write the itinerary

Use the report template below.

---

## Report Template

~~~
# 【城市名】X 天 X 夜旅遊行程
**旅行日期：** YYYY/MM/DD – YYYY/MM/DD
**住宿區域：** ...
**旅行人數：** ...

---

## 行前準備
- 交通票券：...
- 必裝 App：...
- 天氣備註：...
- 重要預訂提醒：...

---

## Day 1｜YYYY/MM/DD（主題）

| 時間 | 地點 | 說明 |
|------|------|------|
| 14:00 | 抵達 / 入住飯店 | 放行李、休息 |
| 15:30 | 景點 A | 說明、小提示 |
| 18:00 | 晚餐：餐廳 B | 推薦菜色、預算 |
| 20:00 | 夜景 / 夜市 C | 自由活動 |

**當日交通說明：** ...
**備用方案（若下雨）：** ...

---

## 實用資訊
| 項目 | 內容 |
|------|------|
| 當地貨幣 | ... |
| 緊急電話 | ... |
| 推薦 SIM / WiFi | ... |

---

## 資料來源
- 來源 1
- 來源 2
~~~

---

## Output Formats

| Format | When to use |
|--------|-------------|
| **Markdown 行程表** | Default text output |
| **HTML 視覺行程頁** | User wants a shareable or printable page |
| **互動地圖** | User wants to see stops on a map |
| **Pass 優化表** | User holds a tourist pass |

---

## Writing Style

- Use clear, practical Traditional Chinese.
- Include 具體時間，避免「上午去 A，下午去 B」這類模糊描述。
- Explain transit steps concretely: 「搭地鐵 2 號線到 XX 站，出 3 號出口，步行約 8 分鐘」。
- Note price ranges in local currency with TWD approximate equivalent.

---

## Quality Checklist

- [ ] All opening hours confirmed
- [ ] Each day's geography is logically clustered
- [ ] Transit time between every stop is estimated
- [ ] Meals are scheduled with realistic time allocations
- [ ] Tourist pass day maximizes value
- [ ] At least one weather-backup option noted per outdoor-heavy day

---

## Example Prompts

請使用 travel-itinerary-planner skill，規劃釜山 5 天 4 夜行程。住在廣安里，持釜山 Pass 24 小時卡。請輸出每日行程表與 HTML 視覺頁面。
