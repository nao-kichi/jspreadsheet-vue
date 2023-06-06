<template>
  <h2>Import Excel data into DB</h2>
  <input type="button" value="行追加" @click="insertRow()" />
  <input type="button" value="行削除" @click="deleteRow()" /><br /><br />

  <Spreadsheet ref="spreadsheet" :license="license" id="spreadsheet">
    <Worksheet :minDimensions="[11, 10]" tableWidth="800" />
  </Spreadsheet><br /><br />
  
  <input type="button" value="ページ作成" @click="create()" />
  <input type="button" value="全て削除" @click="destroy()" /><br /><br />

  <!-- 後に、データ貼り付けで自動保存とする -->
  <input type="button" value="保存" @click="save()" />

</template>

<script>
import { Spreadsheet, Worksheet, jspreadsheet } from "@jspreadsheet/vue";

const license = 'ODg0ZTVlNDg2ZTVhYmFmOTMxMzBjZTAxNjhmZDY4NmI5ZDg1ZTU4ZmNiZjU0NzQ2OGQ2MGYwYjcyZGVmMGU5NWQ1OGFmZTQxMWNhYWI4N2M3YmRhYmNkMTk3Mjc4YzVlMWQzYWMxNjdlZjA0ZTgzZWY0NjNmMTFmOTZlMzQxNjUsZXlKdVlXMWxJam9pU25Od2NtVmhaSE5vWldWMElpd2laR0YwWlNJNk1UWTROVGMxT1RFek5Dd2laRzl0WVdsdUlqcGJJbXB6Y0hKbFlXUnphR1ZsZEM1amIyMGlMQ0pqYjJSbGMyRnVaR0p2ZUM1cGJ5SXNJbXB6YUdWc2JDNXVaWFFpTENKamMySXVZWEJ3SWl3aWQyVmlJaXdpYkc5allXeG9iM04wSWwwc0luQnNZVzRpT2lJek5DSXNJbk5qYjNCbElqcGJJblkzSWl3aWRqZ2lMQ0oyT1NJc0luWXhNQ0lzSW1Ob1lYSjBjeUlzSW1admNtMXpJaXdpWm05eWJYVnNZU0lzSW5CaGNuTmxjaUlzSW5KbGJtUmxjaUlzSW1OdmJXMWxiblJ6SWl3aWFXMXdiM0owSWl3aVltRnlJaXdpZG1Gc2FXUmhkR2x2Ym5NaUxDSnpaV0Z5WTJnaUxDSndjbWx1ZENJc0luTm9aV1YwY3lKZExDSmtaVzF2SWpwMGNuVmxmUT09';

export default {
  components: {
    Spreadsheet,
    Worksheet,
  },
  methods: {
    insertRow() {
      this.$refs.spreadsheet.current[0].insertRow();
    },
    deleteRow() {
      this.$refs.spreadsheet.current[0].deleteRow();
    },
    create() {
      jspreadsheet(document.getElementById('spreadsheet'), {
        worksheets: [{ minDimensions: [11, 10] }]
      });
    },
    destroy() {
      jspreadsheet.destroy(this.$refs.spreadsheet.el);
    }
  },
  data() {
    return {
      license: license,
    };
  }
}
</script>