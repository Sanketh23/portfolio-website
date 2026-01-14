<template>
  <div>
    <div
      id="dark-start"
      :style="{ backgroundColor: startBackgroundColor }"
      :class="{ transition: startTransition }"
    ></div>
    <div id="vanta" class="stationary-background"></div>
    <div class="container">
      <div class="full-title">
        <div class="profile">
          <img src="me.jpg" class="profile-pic" alt="Sanketh Edara" />
        </div>
        <h1
          id="typing-title"
          class="display-4"
          :style="{ zIndex: typingTitleZIndex, color: typingTitleColor }"
          @click="onTitleClick"
        >
          <span class="title">{{ titleText }}</span>
        </h1>
        <div>
          <span>
            <a href="#" @click="popupEmail">Email</a>
          </span>
          •
          <span>
            <a target="_blank" href="https://github.com/sanketh23/">GitHub</a>
          </span>
          •
          <span>
            <a target="_blank" href="https://www.linkedin.com/in/sedara05/"
              >LinkedIn
            </a>
          </span>
        </div>
      </div>

      <div id="project-cards" :class="{ nonexistent: projectCardsNonexistent }">
        <div class="row">
          <div class="col-md-4 card-col">
            <div class="card">
              <div class="card-block">
                <div class="card-title" style="margin-top: 8px;">
                  <img
                    class="company-logo"
                    src="qualcomm.png"
                    @click="popupQualcomm"
                  />
                </div>
                <br />
                <h5 class="card-subtitle">Interim Engineering Intern</h5>
                <div class="card-text">May 2025 - Aug 2025</div>
                <div class="card-buttons">
                  <button
                    type="button"
                    class="btn btn-outline-light"
                    @click="popupQualcomm"
                  >
                    More Info
                  </button>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 card-col">
            <div class="card">
              <div class="card-block">
                <div class="card-title" style="margin-top: 8px;">
                  <img
                    class="company-logo"
                    src="Caterpillar.png"
                    @click="popupCaterpillar"
                  />
                </div>
                <br />
                <h5 class="card-subtitle">AI/ML Software Engineering Co-Op</h5>
                <div class="card-text">Aug 2023 - May 2024</div>
                <div class="card-buttons">
                  <button
                    type="button"
                    class="btn btn-outline-light"
                    @click="popupCaterpillar"
                  >
                    More Info
                  </button>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4 card-col">
            <div class="card">
              <div class="card-block">
                <div class="card-title" style="margin-top: 8px;">
                  <img
                    class="company-logo"
                    src="beacon.png"
                    @click="popupBeacon"
                  />
                </div>
                <br />
                <h5 class="card-subtitle">Software Engineering Intern</h5>
                <div class="card-text">May 2024 - Aug 2024</div>
                <div class="card-buttons">
                  <button
                    type="button"
                    class="btn btn-outline-light"
                    @click="popupBeacon"
                  >
                    More Info
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="row">
          <project-card
            title="Rimble"
            button-href="https://github.com/Sanketh23/rimble"
            button-text="View on GitHub"
            secondary-button-href="https://rimble.example.com"
            secondary-button-text="View Site"
          >
            A daily NBA trivia site built as a full-stack app. Supabase powers
            the backend, and the frontend updates each day with a new challenge
            for users.
          </project-card>

          <project-card
            title="Credit Risk Prediction Tool"
            button-href="https://github.com/Sanketh23/credit-risk-ml"
            button-text="View on GitHub"
          >
            A lightweight web app that predicts credit risk based on borrower
            financial data. Users enter key attributes and instantly receive a
            risk score powered by a machine learning model trained on historical
            loan data.
          </project-card>
        </div>

        <div class="row">
          <project-card
            title="Financial Forecasting Tool"
            button-href="https://github.com/Sanketh23/ai-financial-forecasting"
            button-text="View on GitHub"
          >
            A data-driven financial forecasting tool that predicts future
            outcomes based on historical trends. Built to quickly generate
            projections and insights through an intuitive interface.
          </project-card>

          <project-card
            title="Garden Grocery Marketplace"
            button-href="https://github.com/Sanketh23/garden_grocery"
            button-text="View on Github"
          >
            A local garden grocery marketplace that connects home growers with
            nearby buyers. Browse fresh produce, list items for sale, and
            discover locally grown food in your area.
          </project-card>
        </div>

        <div class="row">
          <project-card
            title="Rec League Management System"
            button-href="https://github.com/Sanketh23/league-management"
            button-text="View on GitHub"
          >
            A rec league management system for organizing teams, schedules, and
            standings. Coaches and players can easily view games, scores, and
            league updates in one place.
          </project-card>

          <project-card
            title="Farm Sense"
            button-href="https://github.com/Sanketh23/FarmSense"
            button-text="View on GitHub"
          >
            FarmSense is a data-driven tool that helps farmers assess field
            conditions and risks. Uses environmental and historical data to
            support smarter, more informed decisions.
          </project-card>
        </div>

        <div class="row">
          <project-card
            title="SignSense"
            button-href="https://github.com/Sanketh23/SignSense"
            button-text="View on GitHub"
          >
            A sign language recognition tool that translates gestures into
            meaningful output. Built to support more accessible communication
            using computer vision.
          </project-card>

          <project-card
            title="SpeechSimplified"
            button-href="https://github.com/Sanketh23/SpeechSimplified"
            button-text="View on GitHub"
          >
            A speech analysis tool that evaluates and simplifies spoken
            responses. Designed to provide clear, actionable feedback to improve
            communication.
          </project-card>
        </div>
        <br />
        <footer>
          sankethedara,
          <span id="footer-year">{{ year }}</span>
          <br />
          <a href="https://github.com/Sanketh23" target="_blank"
            >View on GitHub</a
          >
        </footer>
      </div>
    </div>
    <!-- /.container -->
  </div>
</template>

<script>
import Cookies from 'js-cookie'
import Typed from 'typed.js'
import Swal from 'sweetalert2'

import ProjectCard from '~/components/ProjectCard.vue'

const Popup = Swal.mixin({
  confirmButtonColor: '#8a614c'
})

export default {
  components: { ProjectCard },
  data: () => ({
    year: new Date().getFullYear(),
    titleText: '',
    typingTitleZIndex: () => 100,
    typingTitleColor: () => '#DDDDDD',
    projectCardsNonexistent: true,
    startBackgroundColor: '#113946',
    startTransition: false
  }),
  mounted() {
    const shouldPlayAnimation = !(Cookies.get('typed') === 'true')

    const sixteenHours = 16 / 24
    Cookies.set('typed', 'true', { expires: sixteenHours })

    if (shouldPlayAnimation) {
      // start the title above the shadow, and as white text
      this.typingTitleZIndex = 100
      this.typingTitleColor = '#ead7bb'

      // execute the animation
      new Typed('.title', {
        strings: ['Sanketh Edara'],
        typeSpeed: 100,
        onComplete: () => {
          // wait a bit, then show the page
          setTimeout(() => this.showPage(), 300)
        }
      })
    } else {
      // forgo the animation, and just show the page
      this.titleText = 'Sanketh Edara'
      this.showPage()
    }
  },
  methods: {
    showPage() {
      // make the elements take up space by removing
      // display: none, without removing opacity 0
      this.projectCardsNonexistent = false

      // get rid of the solid color covering the page
      this.startBackgroundColor = 'transparent'

      // invert title text color
      this.typingTitleColor = '#113946'

      // begin the circle transition
      this.startTransition = true
    },
    popupEmail() {
      Popup.fire({
        title: 'Email me!',
        html:
          '<div style="color: #8a614c; text-align:center;"><a href="mailto:sanketh.edara@gmail.com">sanketh.edara@gmail.com</a></div>'
      })
    },

    popupBeacon() {
      const innerHTML =
        '<p><strong>Tech:</strong> Python, Whisper-1, NLP, ML Pipelines</p>' +
        '<p><strong>QXO (Beacon)</strong> - Software Engineering Intern</p>' +
        '<p>May 2024 - Aug 2024 • Herndon, VA</p>' +
        '<ul style="text-align: left;">' +
        '<li>Designed and deployed an NLP-based Speech Evaluation Tool to analyze presentation clarity, pacing, and filler-word usage using AI models.</li>' +
        '<li>Integrated TF-IDF, Logistic Regression, and BERT embedding pipelines to deliver interpretable, accurate AI-driven scoring.</li>' +
        '<li>Standardized onboarding feedback with AI automation, reducing manual evaluation effort by 75%.</li>' +
        '</ul>'
      Popup.fire({
        html: innerHTML,
        imageUrl: 'beacon.png'
      })
    },

    popupCaterpillar() {
      const innerHTML =
        '<p><strong>Tech:</strong> Python, R, ML Modeling, Data Science</p>' +
        '<p><strong>Caterpillar Inc.</strong> - AI/ML Software Engineering Co-Op</p>' +
        '<p>Aug 2023 - May 2024 • West Lafayette, IN</p>' +
        '<ul style="text-align: left;">' +
        '<li>Developed ML models (NBEATS, ARIMA, LSTM) for EV charging vehicles, achieving 87% accuracy for State of Charge, Current, and Voltage.</li>' +
        '<li>Integrated predictive analytics dashboards with Flutter and Firebase to deliver real-time operational insights.</li>' +
        '<li>Improved EV fleet management efficiency using AI-driven forecasting to reduce operational uncertainty.</li>' +
        '</ul>'
      Popup.fire({
        html: innerHTML,
        imageUrl: 'Caterpillar.png'
      })
    },

    popupQualcomm() {
      const innerHTML =
        '<p><strong>Tech:</strong> C++, Java, Android Dev</p>' +
        '<p><strong>Qualcomm Technologies, Inc.</strong> - Interim Engineering Intern</p>' +
        '<p>May 2025 - Aug 2025</p>' +
        '<ul style="text-align: left;">' +
        '<li>Worked on XR glasses platform with real-time orientation tracking and power-efficient sensor fusion.</li>' +
        '<li>Developed and deployed an Extended Kalman Filter on the Hexagon DSP (Snapdragon SM8150) for real-time orientation estimation.</li>' +
        '<li>Integrated with Qualcomm Sensor Execution Environment to extract accelerometer and gyroscope data.</li>' +
        '<li>Optimized EKF using Hexagon Vector Extensions, reducing latency and improving DSP efficiency by 30%.</li>' +
        '<li>Delivered major power savings by offloading CPU to DSP: CPU peak 1.09W vs DSP peak 0.16W (85% reduction), CPU avg 0.724W vs DSP avg 0.073W (90% reduction).</li>' +
        '</ul>'
      Popup.fire({
        html: innerHTML,
        imageUrl: 'qualcomm.png'
      })
    },

    onTitleClick() {
      if (this.projectCardsNonexistent) {
        // forgo the animation, and just show the page
        this.titleText = 'Sanketh Edara'
        this.showPage()
      } else {
        this.popupReplayAnimation()
      }
    },

    popupReplayAnimation() {
      Popup.fire({
        title: 'Want to see the typing intro animation again?',
        type: 'question',
        showCancelButton: true,
        confirmButtonText: 'Yes',
        cancelButtonText: 'No'
      }).then((result) => {
        if (result.value) {
          Cookies.set('typed', 'false')
          location.reload()
        }
      })
    }
  }
}
</script>

<style>
/*
 *	Main
 */
body {
  padding-bottom: 2rem;
  color: #113946;
  /* light color: #dddddd; */
  text-align: center;
}

.stationary-background {
  background: #8a614c;
  background-repeat: no-repeat;
  width: 100%;
  top: -80px;
  bottom: -80px;
  position: fixed;
  z-index: -1;
}

#dark-start {
  opacity: 1;
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0px;
  left: 0px;
  z-index: 1;
  pointer-events: none;
}

#dark-start:before {
  content: '';
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  border-radius: 100%;
  animation-duration: 1s;
  box-shadow: 0px 0px 0px 100vmax #113946;
  width: 150vmax;
  height: 150vmax;
}

.transition:before {
  animation-name: spotlight;
}

.nonexistent {
  display: none;
}

@keyframes spotlight {
  from {
    width: 0vmin;
    height: 0vmin;
  }

  to {
    width: 150vmax;
    height: 150vmax;
  }
}

/*
 *	Header
 */
.full-title {
  padding-top: 0.5rem;
  padding-bottom: 1rem;
  font-size: 1.1rem;
}

.profile {
  display: inline-block;
  margin: 1rem 0;
}

.profile-pic {
  height: 130px;
  border-radius: 50%;
}

.breathe::before {
  content: '';
  position: absolute;
  z-index: -1;
  height: 130px;
  width: 130px;
  border-radius: 50%;
  box-shadow: inset 0 0 0 16px rgba(0, 0, 0, 0.3);
  animation: breathe 16s infinite;
}

@keyframes breathe {
  from,
  75%,
  to {
    transform: scale(1, 1);
  }

  25%,
  50% {
    transform: scale(1.25, 1.25);
  }
}

.full-title a,
a:active,
a:visited {
  display: inline-block;
  /* dark color: #113946; */
  color: #113946;
  transition: all 0.2s ease-in-out;
}

a:hover {
  transform: scale(1.05);
}

body {
  font-family: 'Jost', sans-serif;
  font-weight: 400;
}

.full-title .display-4 {
  font-family: 'Jost', sans-serif;
  font-weight: 500;
  font-size: 2.5em;
  font-style: italic;
}

span.avoidwrap {
  display: inline-block;
}

#typing-title {
  position: relative;
  margin-bottom: 12px;
  transition: all 0.2s ease-in;
}

.company-logo {
  max-width: 62.5%;
  max-height: 105px;
}

/* fix line appearing between buttons */
.card a:hover {
  color: transparent;
}

.card-buttons {
  margin-top: 0.8em;
}

.btn-outline-light {
  /* dark color: #113946; */
  color: #113946;
  /* dark border-color: #113946; */
  border-color: #113946;
  margin-bottom: 0.3em;
}

/*
 *	SweetAlert
 */
#swal2-content {
  text-align: left;
  font-weight: normal;
}

#swal2-content a {
  color: #8a614c;
}

#swal2-content a:hover {
  text-decoration: underline;
}

.swal2-image {
  margin-top: -1.25em;
  margin-left: -1.25em;
  max-width: calc(100% + 2.5em);
  border-radius: 5px 5px 0px 0px;
}

/*
 *	Typed.js
 */
.typed-cursor {
  opacity: 1;
  -webkit-animation: blink 0.7s infinite;
  -moz-animation: blink 0.7s infinite;
  animation: blink 0.7s infinite;
}

@keyframes blink {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
