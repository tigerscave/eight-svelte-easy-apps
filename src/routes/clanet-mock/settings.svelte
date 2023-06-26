<!--カスタム設定編集ボタン-->
<div class="changeSettingsContainer">
  <div>
    <p>レバー設定</p>
  </div>
  <div>
    <p>レバー２</p>
    <select id="lever-list-2" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="伸縮">伸縮</option>
      <option value="S">S</option>
      <option value="M">M</option>
      <option value="起伏">起伏</option>
    </select>
  </div>
  <div>
    <p>レバー３</p>
    <select id="lever-list-3" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="伸縮">伸縮</option>
      <option value="S">S</option>
      <option value="M">M</option>
      <option value="起伏">起伏</option>
    </select>
  </div>
  <div>
    <p>レバー４</p>
    <select id="lever-list-4" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="伸縮">伸縮</option>
      <option value="S">S</option>
      <option value="M">M</option>
      <option value="起伏">起伏</option>
    </select>
  </div>
  <div>
    <p>レバー５</p>
    <select id="lever-list-5" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="伸縮">伸縮</option>
      <option value="S">S</option>
      <option value="M">M</option>
      <option value="起伏">起伏</option>
    </select>
  </div>
</div>
<div class="changeSettingsContainer">
  <div>
    <p>ペダル設定</p>
  </div>
  <div>
    <p>ペダルA</p>
    <select id="pedal-list-A" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="S">S</option>
      <option value="伸縮">伸縮</option>
    </select>
  </div>
  <div>
    <p>ペダルB</p>
    <select id="pedal-list-B" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="S">S</option>
      <option value="伸縮">伸縮</option>
    </select>
  </div>
  <div>
    <p>ペダルC</p>
    <select id="pedal-list-C" class="groups-select-item" disabled>
      <option value="未選択">未選択</option>
      <option value="S">S</option>
      <option value="伸縮">伸縮</option>
    </select>
  </div>
</div>
<div class="save-box">
  <button type="button" class="edit-settings" id="edit-button"
    >カスタム設定を編集</button
  >
</div>

<style>
  .save-box,
  .edit-settings {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .edit-settings {
    width: 11rem;
    height: 2.3rem;
    margin-top: 2rem;
    background: white;
    border: 1px solid black;
  }
  button:active {
    transform: translateY(1px);
  }

  .changeSettingsContainer {
    display: flex;
    justify-content: space-between;
  }

  .groups-select-item {
    width: 6.2rem;
    height: 2.3rem;
  }

  .edit-settings,
  .groups-select-item {
    cursor: pointer;
  }

  /* #settingsPanel {
  display: none;
} */
</style>
