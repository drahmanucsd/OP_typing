```bash
openai tools fine_tunes.prepare_data -f training_data.jsonl
```





# Install Instructions

1. Clone the repository:

```bash
   git clone <repo-url>
```

2.	Navigate to the project directory:
```bash
cd <repo-name>
```

3.	Create and activate a virtual environment:
```bash
python -m venv myenv
```
```bash
source myenv/bin/activate
```
On Windows use: 
```
 myenv\Scripts\activate
```

4.	Install dependencies:
```bash
pip install -r requirements.txt
```
This setup ensures anyone can easily replicate the environment by installing the dependencies from `requirements.txt`.
















# Training model:

2. **Upload Your Training Data:**

   ```bash
   openai tools fine_tunes.prepare_data -f training_data.jsonl
   ```

   This command checks your data for any issues.

3. **Start Fine-Tuning:**

   ```bash
   openai api fine_tunes.create -t "training_data_prepared.jsonl" -m "davinci"
   ```

   Replace `"davinci"` with the base model you wish to fine-tune (e.g., `"ada"`, `"babbage"`, `"curie"`, `"davinci"`).

4. **Monitor Fine-Tuning Job:**

   The command will output a job ID you can use to check the status:

   ```bash
   openai api fine_tunes.get -i <YOUR_FINE_TUNE_JOB_ID>
   ```

5. **Wait for Completion:**

   Once the fine-tuning is complete, the command will display the name of your fine-tuned model.

**Note:** Fine-tuning can take some time depending on the size of your dataset and the model you choose.

