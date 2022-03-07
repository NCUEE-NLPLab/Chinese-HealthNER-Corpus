# Chinese HealthNER Corpus

Chinese <strong>Health</strong>care <strong>N</strong>amed <strong>E</strong>ntity <strong>R</strong>ecognition <strong>(HealthNER)</strong> Corpus is collected and annotated by NCUEE NLP Lab. (http://nlp.ee.ncu.edu.tw/)  

We firstly crawled articles from websites that provide healthcare information, online health-related news and medical question/answer forums. We then removed all HTML tags, images, videos and embedded web advertisements and split the remaining texts into several sentences. We randomly selected partial sentences to retain content diversity for manual annotation.

A total of 10 entity types are described and some examples are provided in Table 1 for healthcare named entity annotation. Three undergraduate students majoring in Chinese language were trained in word segmentation and the named entity tagging task. Inter-annotator agreement is 84.1%. All annotators were asked to discuss differences and seek consensus. Finally, we had 2,531 testing sentences with 7,305 named entities. Each sentence contains an average of 47.92 characters or 28.67 words, and an average of 2.89 named entities. When the agreement was reached, each annotator was then asked to process the remaining sentences individually. As a result, there were 28,161 training sentences, each with an average of 49.44 characters or 29.99 words, and 2.17 named entities.<br><br>

|Entity Type|Description|Examples|
|:---:|:---|:---|
|Body<br>(人體)          |The whole physical structure that forms a person or animal including biological cells, organizations, organs and systems.<br>|“細胞核” (nucleus), “神經組織” (nerve tissue), “左心房” (left atrium), “脊髓” (spinal cord), “呼吸系統” (respiratory system)|
|Symptom<br>(症狀)       |Any feeling of illness or physical or mental change that is caused by a particular disease.                              |“流鼻水” (rhinorrhea), “咳嗽” (cough), “貧血” (anemia), “失眠” (insomnia), “心悸” (palpitation), “耳鳴” (tinnitus)          |
|Instrument<br>(醫療器材)|A tool or other device used for performing a particular medical task such as diagnosis and treatments.                   |“血壓計” (blood pressure meter), “達文西手臂” (DaVinci Robots), “體脂肪計” (body fat monitor), “雷射手術刀” (laser scalpel) |
|Examination<br>(檢驗)   |The act of looking at or checking something carefully in order to discover possible diseases.                            |“聽力檢查” (hearing test), “腦電波圖” (electroencephalography;EEG), “核磁共振造影” (magnetic resonance imaging; MRI) |
|Chemical<br>(化學物質)  |Any basic chemical element typically found in the human body.                                                            |“去氧核糖核酸” (deoxyribonucleic acid; DNA), “糖化血色素”(glycated hemoglobin), “膽固醇” (cholesterol), “尿酸” (uric acid)            |
|Disease<br>(疾病)       |An illness of people or animals caused by infection or a failure of health rather than by an accident.                   |“小兒麻痺症” (poliomyelitis; polio), “帕金森氏症” (Parkinson’s disease), “青光眼” (glaucoma), “肺結核” (tuberculosis)            |
|Drug<br>(藥品)          |Any natural or artificially made chemical used as a medicine.                                                            |“ 阿 斯匹靈 ” (aspirin), “ 普拿疼 ” (acetaminophen), “ 青黴素 ” (penicillin), “流感疫苗” (influenza vaccination)           |
|Supplement<br>(營養品)  |Something added to something else to improve human health.                                                               |“維他命” (vitamin), “膠原蛋白” (collagen), “益生菌” (probiotics), “葡萄糖胺” (glucosamine), “葉黃素” (lutein)           |
|Treatment<br>(治療)     |A method of behavior used to treat diseases.                                                                             |“藥物治療” (pharmacotherapy), “胃切除術” (gastrectomy), “標靶治療” (targeted therapy), “外科手術” (surgery)            |
|Time<br>(時間)          |Element of existence measured in minutes, days, years.                                                                   |“ 嬰兒期 ” (infancy), “ 幼兒時期 ” (early childhood), “ 青春期 ”(adolescence), “生理期” (on one’s period), “孕期” (pregnancy)           |

<br>In summary, our constructed Chinese HealthNER corpus includes 30,692 sentences with a total of around 1.5 million characters or 91.7 thousand words. Table 2 shows detailed statistics of mutually exclusive training and test sets. The entity type distribution in training and test sets is similar. The most common type was BODY (26,413 cases or 38.58% of the total), followed by the SYMP (12,904 cases), DISE (10,079 cases) and CHEM (6,834 cases). These 4 most common types of named entities thus accounted for about 82% of the total 68,460 entities, with the remaining 6 types accounting for 18%.<br><br>

|Entity Type (Tag)|#Train (Ratio%)|#Test (Ratio%)|
|:---:|:---:|:---:|
|Body (BODY)        |23,240 (38.01%)|3,171 (43.41%)|
|Symptom (SYMP)     |11,423 (18.67%)|1,481 (20.27%)|
|Instrument (INST)  |1,047 (1.71%)  |42 (0.58%)    |
|Examination (EXAM) |2,218 (3.63%)  |404 (5.53%)   |
|Chemical (CHEM)    |6,090 (9.96%)  |744 (10.18%)  |
|Disease (DISE)     |9,074 (14.84%) |1,005 (13.76%)|
|Drug (DRUG)        |2,146 (3.51%)  |79 (1.08%)    |
|Supplement (SUPP)  |1,403 (2.29%)  |122 (1.67%)   |
|Treatment (TREAT)  |2,905 (4.75%)  |203 (2.78%)   |
|Time (TIME)        |1,609 (2.63%)  |54 (0.74%)    |
|Total              |61,155 (100%)  |7,305 (100%)  |

<br>

## Data format 資料格式

- id : <String> a sentence identifier
- genre : <String> genres of written textsm including "ft" (formal texts) and "sm" (social media) 
- sentence : <String> a sentence is represented in terms of character sequence 
- word : <List> a list of segmented word sequence
- word_label : <List> a list of the correpsonding word labels
	
## Example 範例

{<br>
&emsp;&emsp;&emsp;&emsp;"id": "00002",<br>
&emsp;&emsp;&emsp;&emsp;"genre": "sm",<br>
&emsp;&emsp;&emsp;&emsp;"sentence": "如何治療胃食道逆流症？",<br>
&emsp;&emsp;&emsp;&emsp;"word": ["如何", "治療", "胃食道逆流症", "？"],<br>
&emsp;&emsp;&emsp;&emsp;"word_label": ["O", "O", "DISE", "O"]<br>
}<br>

{<br>
&emsp;&emsp;&emsp;&emsp;"id": "09877",<br>
&emsp;&emsp;&emsp;&emsp;"genre": "ft",<br>
&emsp;&emsp;&emsp;&emsp;"sentence": "修復肌肉與骨骼最重要的便是熱量、蛋白質與鈣質。",<br>
&emsp;&emsp;&emsp;&emsp;"word": ["修復", "肌肉", "與", "骨骼", "最", "重要", "的", "便是", "熱量", "、", "蛋白質", "與", "鈣質", "。"],<br>
&emsp;&emsp;&emsp;&emsp;"word_label": ["O", "BODY", "O", "BODY", "O", "O", "O", "O", "O", "O", "CHEM", "O", "CHEM", "O"]<br>
}<br>

## Reference 參考文獻  

For more information please refer to our IEEE JBHI Paper: https://ieeexplore.ieee.org/document/9312396

Lung-Hao Lee and Yi Lu (2021). Multiple Embeddings Enhanced Multi-Graph Neural Networks for Chinese Healthcare Named Entity Recognition. IEEE Journal of Biomedical and Health Informatics, 25(7), pp. 2801-2810. https://doi.org/10.1109/JBHI.2020.3048700

@ARTICLE{Lee-IEEEJBHI-2021,<br>
&emsp;&emsp;&emsp;&emsp;author  = {Lung-Hao Lee and Yi Lu},<br>
&emsp;&emsp;&emsp;&emsp;title   = {Multiple Embeddings Enhanced Multi-Graph Neural Networks for Chinese Healthcare Named Entity Recognition},<br>
&emsp;&emsp;&emsp;&emsp;journal = {IEEE Journal of Biomedical and Health Informatics},<br>
&emsp;&emsp;&emsp;&emsp;volume  = 25,<br>
&emsp;&emsp;&emsp;&emsp;number  = 7,<br>
&emsp;&emsp;&emsp;&emsp;pages   = {2801 -2810},<br>
&emsp;&emsp;&emsp;&emsp;month   = 7,<br>
&emsp;&emsp;&emsp;&emsp;year    = 2021,<br>
&emsp;&emsp;&emsp;&emsp;url     = { https://doi.org/10.1109/JBHI.2020.3048700 }<br>
}     
