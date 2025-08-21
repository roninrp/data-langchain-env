# ⚙️ Setting up LangChain 🦜🔗

## 🎯 Goal of this challenge

Setting up a separate environment for our LLM applications.

In this unit we need a lot of new packages. Some of these packages are not compatible with the package versions we needed for other parts of the bootcamp.

So we will set up a new virtual environment. That way we have two separate python environments, and our packages will not conflict. 🦾

This is something you will often do for your projects: create dedicated virtual environments.

## 🐍 Create a new virtual environment

🐍 Create the virtual env

```bash
cd ~/code/<user.github_nickname>/{{local_path_to("06-Deep-Learning/07-GenAI-and-RAG/00-LangChain-Env")}}
cd .. # Move to the unit's main folder
python --version # First, check your Python version for <YOUR_PYTHON_VERSION> below (e.g. 3.12.9)
pyenv virtualenv <YOUR_PYTHON_VERSION> langchain-env
pyenv local langchain-env
pip install --upgrade pip
```

Then, make sure your Terminal displays `[🐍 langchain-env]` to the right.

## 📦 Install the packages

Navigate back to this challenge's folder:

```bash
cd ~/code/<user.github_nickname>/{{local_path_to("06-Deep-Learning/07-GenAI-and-RAG/00-LangChain-Env")}}
```

In this folder, we created a `requirements.txt` file with all the requirements for this unit's challenges. We just need to `pip install` it to have all of them:

```bash
pip install -r requirements.txt
```

In essence we are installing:
- Jupyter Notebook and all its dependencies
- Classics like Pandas and NumPy
- `google-genai` to interact directly with Google's Gemini LLM
- `langchain`
- `langchain-google-genai` so we can use Gemini throug LangChain
- `langchain-community` with extra tools
- `langchain-chroma`, a vector store
- `pypdf`, to load pdf files

## 🔑 Google Gemini API key

In this unit's challenges we'll make use of Gemini, Google's flagship LLM.

Gemini has a free tier that should be sufficient for our use cases. No need to set up billing for this, but we will need to sign up to get an API key for Google's Gemini API.

Let's get started:

1. Browse to `https://aistudio.google.com/apikey`
1. If you aren't signed in with your Google account yet, sign in.
1. In the top right corner, click on the blue `Create API key`.
1. Follow the steps to create your API key. Remember: no need to set up billing, we will stick to the free tier.

We don't want to save our personal API key straight into the notebooks and `.py` files we'll create. Think about: we might want to share our code later on with others, but they shouldn't get our API keys.

Instead, we will save the key in a separate file `.env`. We will then load the key from that file into memory so that the libraries can use it when they need to authenticate with the Gemini API.

Let's do this:

1. Make sure you're in this challenge's folder:

```bash
cd ~/code/<user.github_nickname>/{{local_path_to("06-Deep-Learning/07-GenAI-and-RAG/00-LangChain-Env")}}
```

2. Copy the `.env.sample` file into a new `.env.` file in the folder that will contain all of this unit's challenges:

    ```bash
    cp .env.sample ../.env
    ```

1. Open the `.env` file with your favourite code editor:

    ```bash
    code ../.env
    ```

1. Replace `your_gemini_api_key` with the API key you obtained.

1. Save the file and close it.


## ✅ Check your installation

```bash
jupyter notebook check.ipynb
```

## 🏁 Finished

You now have a fresh environment to work with LLMs.

Just remember to always check that you are using the `langchain-env` environment. Especially when you are using VS Code, make sure to select this new environment.

Don't forget to commit and push this challenge.
