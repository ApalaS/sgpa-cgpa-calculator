<template>
  <div class="container">
    <h1
      class="heading is-size-3 has-text-centered is-underlined has-text-weight-bold is-family-monospace"
    >
      SGPA-CGPA CALCULATOR
    </h1>
    <div class="box mt-6 tabs is-toggle is-toggle-rounded is-centered">
      <ul>
        <li @click="show = false" :class="{ 'is-active': !show }">
          <a>
            <span class="icon is-small"
              ><i class="fas fa-graduation-cap"></i
            ></span>
            <span>SGPA</span>
          </a>
        </li>
        <li @click="show = true" :class="{ 'is-active': show }">
          <a>
            <span class="icon is-small"
              ><i class="fas fa-graduation-cap"></i
            ></span>
            <span>CGPA</span>
          </a>
        </li>
      </ul>
    </div>
    <div class="scroll">
      <table class="center table is-hoverable is-striped">
        <tr>
          <th>
            Course Code:
          </th>
          <th>
            Semester:
          </th>
          <th>credits:</th>
          <th>grade:</th>
        </tr>
        <tr v-for="(row, index) in subjects" :key="index">
          <td>
            <input
              v-model="subjects[index].course"
              class="input"
              type="text"
              placeholder="Enter course code"
            />
          </td>
          <td>
            <select
              v-model="subjects[index].sem"
              class="input"
              placeholder="Enter sem"
            >
              <option value="#" disabled selected hidden></option>
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
              <option value="4">4</option>
              <option value="5">5</option>
              <option value="6">6</option>
              <option value="7">7</option>
              <option value="8">8</option>
            </select>
          </td>
          <td>
            <input
              v-model="subjects[index].credits"
              class="input"
              type="number"
              placeholder="Enter course credits"
              max="4"
              min="0"
            />
          </td>
          <td>
            <select v-model="subjects[index].grade" class="input">
              <option value="#"></option>
              <option value="S">S</option>
              <option value="A">A</option>
              <option value="B">B</option>
              <option value="C">C</option>
              <option value="D">D</option>
              <option value="F">F</option>
            </select>
          </td>
          <td>
            <button
              @click="deleteRow(index)"
              class="button is-danger is-outlined"
            >
              <i class="fas fa-trash"></i>
            </button>
          </td>
        </tr>
      </table>
    </div>
    <div class="addBtn">
      <button
        @click="addRow"
        class="add button is-fullwidth  is-info is-outlined"
      >
        <i class="fas fa-plus"></i>Add Subject
      </button>
    </div>
    <div class="calculate">
      <button @click="calculateSgpa" class="calc button is-fullwidth  is-info">
        Calculate
      </button>
    </div>
    <div class="result">
    Total Credits:
    </div>
    <div class="result"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      result: null,
      subjects: [
        {
          course: null,
          sem: null,
          credits: null,
          grade: null,
        },
      ],
    };
  },
  methods: {
    addRow: function() {
      this.subjects.push({
        course: null,
        sem: null,
        credits: null,
        grade: null,
      });
    },
    deleteRow: function(index) {
      this.subjects.splice(index, 1);
      console.log(this.deleteRow);
    },
    calculateSgpa: function(){
      // if sem is same => S=10 A=9...
      // credits*grade/credits
      //forEach((ele) => {})
    }
  },
};
</script>

<style scoped>
.scroll {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 100%;
  max-height: 40vh;
  overflow-y: scroll;
}
.add {
  max-width: 60vh;
}
.addBtn {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 20px;
}
.calculate {
  padding-top: 20px;
  display: flex;
  justify-content: center;
}
.calc{
  max-width: 20vh;
}
</style>
