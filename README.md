# Designing Logic Pattern Templates for Counter-Argument Logical Structure Analysis
## Currently only the formatted dataset is uploaded, other additional material will be added soon.

## Contents

- **train.json**: training set containing 516 CAs with only single-template label per sentence.
- **dev.json**: dev set containing 128 CAs with only single-template label per sentence.
- **test.json**: test set containing 134 CAs with at least one multi-template label sentence, the other sentences have single-template labels.

## The meaning of each field in the json files

- **pm_id**: id for the initial-argument.
- **lo_id**: id for the counter-argument.
- **pm_speech**: essay of an initial-argument.
- **lo_speech**: essay of a counter-argument, divided by sentences.
- **ptns**: template label for each sentence.
- **segments**: segments for different templates. A segment is considered as one or more consecutive sentences with the same template.
  - **key for each segment**: template id.
  - **range**: start_index, end_index of of counter-argument sentences in lo_speech.
  - **slots**: slot-fillers for the corresponding template.

**In the test set, we do not have a segment field since there are multiple ways of deciding segments due to the presence of multi-template labels. Therefore, the test set has the following fields instead.**

- **slots**: non-expert annotators raw annotations of slot-fillers for the corresponding CA.
- **workers_raw_annotations**: non-expert annotators raw annotations of logic templates for corresponding CA.
- **filtered_slots**: slot-fillers filtered from the raw slots based on the rules 1) discarding slots that are cannot be exactly found from the CA essay; 2) discarding slots that subset of other slots.

## Template id - name mapping

- 1: Mitigation (Mig)
- 2: Alternative (Alt)
- 3: No evidence (No Evi)
- 4: Another true cause (ATC)
- 5: Missing mechanism #1 (MM1)
- 6: Missing mechanism #2 (MM2)
- 7: No need to address (NNA)
- 8: Negative effect due to y (Neg eff)
- 9: Positive effects of a different perspective from y #1 (Dif Per1)
- 10: Positive effects of a different perspective from y #2 (Dif Per2)
- 11: Others
- 100: Non-argumentative
