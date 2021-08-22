<script lang="ts">
  import "medblocks-ui/dist/medblocks";
  import "@shoelace-style/shoelace/dist/themes/base.css";
  import axios from "axios";

  const ehrId = "b82bc077-4129-4020-884d-e9028223af1c";
  const templateId= 'Covid.form.v3';
  
  const handleSubmit = async (e: any) => {
    const detail = await axios.post(
      "http://localhost/ehrbase/rest/ecis/v1/composition",
      e.detail,{
          params: { format: "FLAT", templateId, ehrId }
      });
    console.log(detail.data);
  };
</script>

<main>
  <h2>Covid Form</h2>
  <mb-form ref="formRef" on:mb-submit={handleSubmit}>
    <mb-context path="covid.form.v1/category" />
    <mb-context path="covid.form.v1/context/start_time" />
    <mb-context path="covid.form.v1/context/setting" />
    <mb-select
      path="covid.form.v1/clinical_background/covid_19_admission/hospital_admission_status"
      label="Hospital admission status"
    >
      <mb-option value="at0003" label="YES" />
      <mb-option value="at0004" label="NO" />
      <mb-option value="at0005" label="UNKNOWN" />
    </mb-select>
    <mb-date
      time
      path="covid.form.v1/clinical_background/covid_19_admission/date_first_admitted"
      label="Date first admitted"
    />
    <mb-context
      path="covid.form.v1/clinical_background/covid_19_admission/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/covid_19_admission/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/covid_19_admission/encoding"
    />

    <mb-input
      textarea
      path="covid.form.v1/clinical_background/age/comment"
      label="Comment"
    />
    <mb-context path="covid.form.v1/clinical_background/age/time" />
    <mb-context path="covid.form.v1/clinical_background/age/subject" />
    <mb-context path="covid.form.v1/clinical_background/age/language" />
    <mb-context path="covid.form.v1/clinical_background/age/encoding" />
    <mb-input
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/screening_purpose"
      label="Screening purpose"
    />
    <mb-select
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/presence_of_any_symptoms_or_signs"
      label="Presence of any symptoms or signs?"
    >
      <mb-option value="at0031" label="Present" />
      <mb-option value="at0032" label="Absent" />
      <mb-option value="at0033" label="Unknown" />
    </mb-select>
    <mb-date
      time
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/onset_of_any_symptoms_or_signs"
      label="Onset of any symptoms or signs"
    />
    <mb-input
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/description"
      label="Description"
    />
    <mb-input
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/specific_symptom_sign:0/symptom_or_sign_name"
      label="Symptom or sign name"
    />
    <mb-select
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/specific_symptom_sign:0/presence"
      label="Presence?"
    >
      <mb-option value="at0023" label="Present" />
      <mb-option value="at0024" label="Absent" />
      <mb-option value="at0027" label="Unknown" />
    </mb-select>
    <mb-input
      textarea
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/specific_symptom_sign:0/comment"
      label="Comment"
    />
    <mb-input
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/overall_comment"
      label="Overall comment"
    />
    <mb-context
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/any_event:0/time"
    />
    <mb-context
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/symptom_sign_screening_questionnaire/encoding"
    />
    <mb-input
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/screening_purpose"
      label="Screening purpose"
    />
    <mb-select
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/presence_of_any_conditions"
      label="Presence of any conditions?"
    >
      <mb-option value="at0031" label="Present" />
      <mb-option value="at0032" label="Absent" />
      <mb-option value="at0033" label="Unknown" />
    </mb-select>
    <mb-input
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/specific_condition:0/condition_name"
      label="Condition name"
    />
    <mb-select
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/specific_condition:0/presence"
      label="Presence?"
    >
      <mb-option value="at0023" label="Present" />
      <mb-option value="at0024" label="Absent" />
      <mb-option value="at0027" label="Unknown" />
    </mb-select>
    <mb-date
      time
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/specific_condition:0/onset"
      label="Onset"
    />
    <mb-input
      textarea
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/specific_condition:0/comment"
      label="Comment"
    />

    <mb-select
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/pregnancy_gestation/coded_text_value"
      label="Pregnancy gestation"
    >
      <mb-option value="at0036" label="First trimester" />
      <mb-option value="at0037" label="Second trimester" />
      <mb-option value="at0038" label="Third trimester" />
    </mb-select>
    <mb-input
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/overall_comment"
      label="Overall comment"
    />
    <mb-context
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/any_event:0/time"
    />
    <mb-context
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/condition_screening_questionnaire/encoding"
    />
    <mb-input
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/screening_purpose"
      label="Screening purpose"
    />
    <mb-input
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/specific_management_treatment_activity:0/activity_name"
      label="Activity name"
    />
    <mb-select
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/specific_management_treatment_activity:0/actioned"
      label="Actioned?"
    >
      <mb-option value="at0023" label="Actioned" />
      <mb-option value="at0024" label="Not actioned" />
      <mb-option value="at0027" label="Unknown" />
    </mb-select>
    <mb-date
      time
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/specific_management_treatment_activity:0/date_actioned"
      label="Date actioned"
    />
    <mb-input
      textarea
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/specific_management_treatment_activity:0/comment"
      label="Comment"
    />
    <mb-input
      textarea
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/overall_comment"
      label="Overall comment"
    />
    <mb-context
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/any_event:0/time"
    />
    <mb-context
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/management_treatment_screening_questionnaire/encoding"
    />
    <mb-quantity
      default="Cel"
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/any_event:0/temperature"
      label="Temperature"
    >
      <mb-unit unit="Cel" label="Cel" />
      <mb-unit unit="[degF]" label="[degF]" />
    </mb-quantity>
    <mb-input
      textarea
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/any_event:0/comment"
      label="Comment"
    />
    <mb-select
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/any_event:0/body_exposure"
      label="Body exposure"
    >
      <mb-option value="at0031" label="Naked" />
      <mb-option value="at0032" label="Reduced clothing/bedding" />
      <mb-option value="at0033" label="Appropriate clothing/bedding" />
      <mb-option value="at0034" label="Increased clothing/bedding" />
    </mb-select>
    <mb-input
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/any_event:0/description_of_thermal_stress"
      label="Description of thermal stress"
    />

    <mb-input
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/any_event:0/confounding_factors:0"
      label="Confounding factors"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/any_event:0/time"
    />
    <mb-select
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/location_of_measurement"
      label="Location of measurement"
    >
      <mb-option value="at0025" label="Rectum" />
      <mb-option value="at0024" label="Axilla" />
      <mb-option value="at0023" label="Ear canal" />
      <mb-option value="at0061" label="Forehead" />
      <mb-option value="at0022" label="Mouth" />
      <mb-option value="at0026" label="Nasopharynx" />
      <mb-option value="at0027" label="Urinary bladder" />
      <mb-option value="at0028" label="Intravascular" />
      <mb-option value="at0043" label="Skin" />
      <mb-option value="at0051" label="Vagina" />
      <mb-option value="at0054" label="Oesophagus" />
      <mb-option value="at0055" label="Inguinal skin crease" />
      <mb-option value="at0060" label="Temple" />
    </mb-select>
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/body_temperature/encoding"
    />
    <mb-select
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/presence"
      label="Presence"
    >
      <mb-option value="at0063" label="Present" />
      <mb-option value="at0064" label="Not detected" />
    </mb-select>
    <mb-quantity
      default="/min"
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/rate"
      label="Rate"
    >
      <mb-unit unit="/min" label="/min" />
    </mb-quantity>
    <mb-select
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/regularity"
      label="Regularity"
    >
      <mb-option value="at0006" label="Regular" />
      <mb-option value="at0007" label="Irregular" />
    </mb-select>
    <mb-select
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/depth"
      label="Depth"
    >
      <mb-option value="at0017" label="Normal" />
      <mb-option value="at0018" label="Shallow" />
      <mb-option value="at0019" label="Deep" />
      <mb-option value="at0025" label="Variable" />
    </mb-select>
    <mb-input
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/clinical_description"
      label="Clinical description"
    />
    <mb-input
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/clinical_interpretation:0"
      label="Clinical interpretation"
    />
    <mb-input
      texarea
        textarea
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/comment"
      label="Comment"
    />
    <mb-select
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/body_position"
      label="Body position"
    >
      <mb-option value="at0066" label="Standing/upright" />
      <mb-option value="at0067" label="Sitting" />
      <mb-option value="at0068" label="Reclining" />
      <mb-option value="at0069" label="Lying" />
      <mb-option value="at0071" label="Prone" />
    </mb-select>
    <mb-input
      texarea
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/confounding_factors:0"
      label="Confounding factors"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/respiration/any_event:0/time"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/respiration/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/respiration/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/respiration/encoding"
    />

    <mb-percent
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/any_event:0/spo"
      label="Sp02"
      />
    <mb-input
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/any_event:0/interpretation:0"
      label="Interpretation"
    />
    <mb-input
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/any_event:0/confounding_factors:0"
      label="Confounding factors"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/any_event:0/time"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/vital_signs/pulse_oximetry/encoding"
    />
    <mb-select
      path="covid.form.v1/clinical_background/travel_screening_questionnaire/any_event:0/travel"
      label="Travel?"
    >
      <mb-option value="at0006" label="Yes" />
      <mb-option value="at0005" label="No" />
      <mb-option value="at0027" label="Unknown" />
    </mb-select>
    <mb-select
      path="covid.form.v1/clinical_background/travel_screening_questionnaire/any_event:0/domestic_international"
      label="Domestic/international"
    >
      <mb-option value="at0028" label="Domestic travel" />
      <mb-option value="at0029" label="International travel" />
      <mb-option value="at0030" label="Domestic and international travel" />
    </mb-select>
    <mb-context
      path="covid.form.v1/clinical_background/travel_screening_questionnaire/any_event:0/time"
    />
    <mb-context
      path="covid.form.v1/clinical_background/travel_screening_questionnaire/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/travel_screening_questionnaire/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/travel_screening_questionnaire/encoding"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/test_name"
      label="Test name"
    />
    <mb-select
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/overall_test_status"
      label="Overall test status"
    >
      <mb-option value="at0107" label="Registered" />
      <mb-option value="at0037" label="Partial" />
      <mb-option value="at0120" label="Preliminary" />
      <mb-option value="at0038" label="Final" />
      <mb-option value="at0040" label="Amended" />
      <mb-option value="at0115" label="Corrected" />
      <mb-option value="at0119" label="Appended" />
      <mb-option value="at0074" label="Cancelled" />
      <mb-option value="at0116" label="Entered in error" />
    </mb-select>
    <mb-context
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/overall_test_status_timestamp"
      label="Overall test status timestamp"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/diagnostic_service_category"
      label="Diagnostic service category"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/clinical_information_provided"
      label="Clinical information provided"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/conclusion"
      label="Conclusion"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/test_diagnosis:0"
      label="Test diagnosis"
    />
    <mb-input
      textarea
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/comment:0"
      label="Comment"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/confounding_factors:0"
      label="Confounding factors"
    />
    <mb-context
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/any_event:0/time"
    />

    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/laboratory_internal_identifier/text_value"
      label="Laboratory internal identifier"
    />
    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/test_request_details:0/original_test_requested_name:0"
      label="Original test requested name"
    />

    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/test_request_details:0/requester_order_identifier/text_value"
      label="Requester order identifier"
    />

    <mb-input
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/test_request_details:0/receiver_order_identifier/text_value"
      label="Receiver order identifier"
    />
    <mb-checkbox
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/point-of-care_test"
      label="Point-of-care test"
    />
    <mb-context
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/subject"
    />
    <mb-context
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/language"
    />
    <mb-context
      path="covid.form.v1/clinical_background/lab_testing/laboratory_test_result/encoding"
    />
    <mb-select
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/health_risk"
      label="Health risk"
    >
      <mb-option value="at0.1" label="COVID-19 Risk assessment" />
    </mb-select>
    <mb-select
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_factors:0/risk_factor"
      label="Risk factor"
    >
      <mb-option value="at0.9" label="Contact with confirmed Covid-19 case" />
      <mb-option
        value="at0.14"
        label="Potential contact exposure based on location"
      />
      <mb-option
        value="at0.10"
        label="Contact with suspected case/ pneumonia case"
      />
      <mb-option
        value="at0.13"
        label="Contact with severe, unexplained respiratory disease"
      />
      <mb-option value="at0.11" label="Contact with birds in China" />
      <mb-option
        value="at0.12"
        label="Contact with confirmed human case of Avian flu in China"
      />
      <mb-option
        value="at0.18"
        label="Needs admission for respiratory disease"
      />
      <mb-option value="at0.19" label="Other household members are ill" />
      <mb-option
        value="at0.20"
        label="Household members with travel exposure"
      />
    </mb-select>
    <mb-select
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_factors:0/presence"
      label="Presence"
    >
      <mb-option value="at0018" label="Present" />
      <mb-option value="at0019" label="Absent" />
      <mb-option value="at0.15" label="Unknown" />
    </mb-select>
    <mb-input
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_factors:0/description"
      label="Description"
    />
    <mb-date
      time
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_factors:0/date_identified"
      label="Date identified"
    />
    <mb-checkbox
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_factors:0/mitigated"
      label="Mitigated"
    />

    <mb-input
      textarea
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_factors:0/comment"
      label="Comment"
    />
    <mb-select
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/risk_assessment"
      label="Risk assessment"
    >
      <mb-option value="at0.16" label="Low risk" />
      <mb-option value="at0.17" label="High risk" />
    </mb-select>
    <mb-select
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/assessment_type"
      label="Assessment type"
    >
      <mb-option value="at0021" label="Relative risk" />
      <mb-option value="at0022" label="Absolute risk" />
    </mb-select>

    <mb-input
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/rationale"
      label="Rationale"
    />
    <mb-input
      textarea
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/comment"
      label="Comment"
    />
    <mb-date
      time
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/last_updated"
      label="Last updated"
    />
    <mb-input
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/assessment_method"
      label="Assessment method"
    />
    <mb-context
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/subject"
    />
    <mb-context
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/language"
    />
    <mb-context
      path="covid.form.v1/assessment/covid-19_infection_risk_assessment/encoding"
    />
    <mb-input
      path="covid.form.v1/conclusion/problem_diagnosis/problem_diagnosis_name"
      label="Problem/Diagnosis name"
    />
    <mb-input
      path="covid.form.v1/conclusion/problem_diagnosis/clinical_description"
      label="Clinical description"
    />
    <mb-input
      path="covid.form.v1/conclusion/problem_diagnosis/body_site:0"
      label="Body site"
    />
    <mb-date
      time
      path="covid.form.v1/conclusion/problem_diagnosis/date_time_of_onset"
      label="Date/time of onset"
    />
    <mb-date
      time
      path="covid.form.v1/conclusion/problem_diagnosis/date_time_clinically_recognised"
      label="Date/time clinically recognised"
    />
    <mb-select
      path="covid.form.v1/conclusion/problem_diagnosis/severity"
      label="Severity"
    >
      <mb-option value="at0047" label="Mild" />
      <mb-option value="at0048" label="Moderate" />
      <mb-option value="at0049" label="Severe" />
    </mb-select>
    <mb-input
      path="covid.form.v1/conclusion/problem_diagnosis/course_description"
      label="Course description"
    />
    <mb-date
      time
      path="covid.form.v1/conclusion/problem_diagnosis/date_time_of_resolution"
      label="Date/time of resolution"
    />
    <mb-select
      path="covid.form.v1/conclusion/problem_diagnosis/diagnostic_certainty"
      label="Diagnostic certainty"
    >
      <mb-option value="at0074" label="Suspected" />
      <mb-option value="at0075" label="Probable" />
      <mb-option value="at0076" label="Confirmed" />
    </mb-select>
    <mb-input
      textarea
      path="covid.form.v1/conclusion/problem_diagnosis/comment"
      label="Comment"
    />
    <mb-date
      time
      path="covid.form.v1/conclusion/problem_diagnosis/last_updated"
      label="Last updated"
    />
    <mb-context path="covid.form.v1/conclusion/problem_diagnosis/subject" />
    <mb-context path="covid.form.v1/conclusion/problem_diagnosis/language" />
    <mb-context path="covid.form.v1/conclusion/problem_diagnosis/encoding" />
    <mb-context path="covid.form.v1/composer" />
    <mb-context path="covid.form.v1/language" />
    <mb-context path="covid.form.v1/territory" />
    <mb-submit><sl-button >Submit</sl-button></mb-submit>
  </mb-form>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  @media (min-width: 480px) {
  }
</style>
