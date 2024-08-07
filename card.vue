<template>
  <ld-tabs>
    <ld-tab>
      <v-container>
        <card-section>
          <v-col cols="12">
            <h3>Регистрационные данные</h3>
          </v-col>
          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-edit-text
                :column="true"
                label="Рег. номер"
                :labelwidth="true"
              >
                {{ card.attr.RegistrationNumber }}
              </card-edit-text>
            </v-row>

            <v-row class="pl-4">
              <card-datepicker
                label="Рег. дата"
                v-model="card.attr.RegistrationDate"
              />
              <v-icon size="18" color="primary" class="mr-2">date_range</v-icon>
            </v-row>
            
            <v-row class="pl-4">
              <card-textarea
                :labelwidth="true"
                label="Краткое содержание"
              >
                {{ card.attr.Annotation }}
              </card-textarea>
            </v-row>
          </v-col>
        </card-section>

        <card-section>
          <v-col cols="12">
            <h3>Коллегиальный орган</h3>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-combobox
                v-model="card.attr.CollegialBody"
                label="Коллегиальный орган"
              />
            </v-row>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-combobox
                label="Организация"
              />
            </v-row>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-combobox
                label="Председатель"
              />
            </v-row>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-combobox
                label="Заместитель председателя"
              />
            </v-row>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-combobox
                label="Секретарь"
              />
            </v-row>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-combobox
                label="Состав"
              />
            </v-row>
          </v-col>
        </card-section>

        <card-section>
          <v-col cols="12">
            <h3>Иноформация о заседании</h3>
          </v-col>

          <v-col cols="12" class="pl-2">
            <v-row class="pl-4">
              <card-datepicker
                label="Дата проведения"
                v-model="card.attr.Od_MeetingDate"
              />
              <v-icon size="18" color="primary" class="mr-2">date_range</v-icon>
            </v-row>

            <v-row class="pl-4">
              <card-radiogroup
                label="Форма заседания"
                v-model="choice"
                label-size="5"
              >
                <card-radiobutton
                  label="Очная"
                  value="1"
                ></card-radiobutton>
                <card-radiobutton
                  label="Заочная"
                  value="0"
                ></card-radiobutton>
              </card-radiogroup>
            </v-row>

            <v-row class="pl-4">
              <card-textarea
                :labelwidth="true"
                label="Комментарий"
              >
                {{ card.attr.Od_Comments }}
              </card-textarea>
            </v-row>
          </v-col>
        </card-section>
      </v-container>
    </ld-tab>
  </ld-tabs>
</template>

<script>
export default {
  data() {
    return {
      choice: '1',
    };
  },
  created() {
  },
  mounted() {
    console.log(this.card);
  },
  computed: {
    regDate() {
        return new Date(this.card.attr.RegistrationDate).toLocaleDateString();
    }
  }
};
</script>