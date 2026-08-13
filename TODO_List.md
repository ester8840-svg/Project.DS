Steps Before sending to Zev:

1.  1. Hebrew documentation where possible - more its better
   
      Please review the documentation I added, particularly the section covering the PDF generation code.

    2. Add to the project descriptions explanation that we try to make the solution work on CPU 
      to make it cheap and simple to use.


2. OCR-2:

    a. Transform the code and text in the ocr_8_angles_paddleocr.ipynb notebook
    to less AI genereted and mor human
    
    b. summerize and explain why we select PaddleOCR 
   (reasons: Open source, use CPU, research over benchmarks)
   take citation from next benchmarks:
   - https://www.codesota.com/ocr/best-for-python
   - https://pragmile.com/ocr-ranking-2025-comparison-of-the-best-text-recognition-and-document-structure-software/
   - https://unstract.com/blog/best-opensource-ocr-tools/

    c. Explain why we select specific parameters for the OCR model and change the Image resolution

      Benchmarks:
   ```
   text_detection_model_name="PP-OCRv6_small_det",
   text_recognition_model_name="PP-OCRv6_small_rec",
   text_recognition_batch_size=8,
   text_det_limit_side_len=1600, 
   OCR passes: 100%|██████████| 8/8 [03:49<00:00, 28.63s/it, angle=315, image=PDF_Edge_Case_11_pag]
   
   text_detection_model_name="PP-OCRv6_tiny_det",
   text_recognition_model_name="PP-OCRv6_tiny_rec",
   text_recognition_batch_size=16,
   text_det_limit_side_len=1600, 
   OCR passes: 100%|██████████| 8/8 [01:16<00:00,  9.50s/it, angle=315, image=PDF_Edge_Case_11_pag]
   
   text_detection_model_name="PP-OCRv6_tiny_det",
   text_recognition_model_name="PP-OCRv6_tiny_rec",
   text_recognition_batch_size=8,
   text_det_limit_side_len=1600, 
   OCR passes: 100%|██████████| 8/8 [01:12<00:00,  9.09s/it, angle=315, image=PDF_Edge_Case_11_pag]
   
   
   text_detection_model_name="PP-OCRv6_tiny_det",
   text_recognition_model_name="PP-OCRv6_tiny_rec",
   text_recognition_batch_size=8,
   text_det_limit_side_len=1200, Lowering the dataset from 300 to 200 DPI
   OCR passes: 100%|██████████| 8/8 [00:53<00:00,  6.74s/it, angle=315, image=PDF_Edge_Case_11_pag]
   ```

3. REGEX-2:
   a. Transform the code and text in the passport_text_pattern_detector.ipynb notebook
    to less AI genereted and more human

5. Crate description of future DNN model for passports recognition.



DONE:
2. OCR-1: - MAXIM - DONE

    a. DO short research over Python OCR options and describe why we select specific model
    
    b. Create notebook that take open source OCR model and extract text 
    from the images in dataset_images dir for 8 angles by routing the image 8 times 45 degrees
   
    c. Output to DF with 8 texts per image.

4. REGEX-1: - MAXIM - DONE:

    a. DO short research and collect small DB of passport string patterns.
      
   Research docs:
   - https://link.springer.com/chapter/10.1007/978-3-642-03315-5_11
   - https://www.id4africa.com/2019/almanac/GEMALTO-Joseph-Leibenguth.pdf
   - https://www.icao.int/sites/default/files/publications/DocSeries/9303_p4_cons_en.pdf
   - https://eoivienna.gov.in/public_files/assets/pdf/Passport_Photo_Requirements_230125.pdf

    b. Transform the DB to regex.
    
    c. Read OCR outputs and try to find passports by some rating to how many regexes matched. 
