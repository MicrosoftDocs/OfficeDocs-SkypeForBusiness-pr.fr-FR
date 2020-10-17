---
title: Outils du kit de ressources de conversation permanente Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80a9116374914c212d305ef2e55d0b8c4fecb782
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533667"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="b264d-102">Outils du kit de ressources de conversation permanente Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b264d-102">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b264d-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b264d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="b264d-104">Les outils du kit de ressources de conversation permanente Lync Server 2013 facilitent les tâches de routine pour les administrateurs qui déploient et gèrent Lync Server 2013 le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-104">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="b264d-105">Outre les instructions d’installation, cette rubrique décrit l’objet de chaque outil, ainsi que des exemples de son utilisation.</span><span class="sxs-lookup"><span data-stu-id="b264d-105">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="b264d-106">Installation des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="b264d-106">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="b264d-107">Pour installer les outils du kit de ressources Lync Server 2013, téléchargez **PersistentChatReskit.msi**.</span><span class="sxs-lookup"><span data-stu-id="b264d-107">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="b264d-108">Exécutez **PersistentChatReskit.msi** pour effectuer une installation simple.</span><span class="sxs-lookup"><span data-stu-id="b264d-108">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="b264d-109">Le fichier. msi installe tous les outils dans le chemin d’accès suivant : \\ **Program Files \\ Microsoft Lync Server 2013 \\ persistent Server Resource Kit**.</span><span class="sxs-lookup"><span data-stu-id="b264d-109">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="b264d-110">Les outils qui sont des fichiers exécutables autonomes se trouvent dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="b264d-110">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="b264d-111">Les outils qui ont également des fichiers se trouvent dans leurs propres sous-dossiers.</span><span class="sxs-lookup"><span data-stu-id="b264d-111">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b264d-112">Après avoir installé les outils du kit de ressources Lync Server 2013, vous devez installer <STRONG>PsExec.exe</STRONG> et copier <STRONG>PsExec.exe</STRONG> dans le chemin d’accès suivant : \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ persistent Server Resource Kit\ChatStressTool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b264d-112">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="b264d-113">Si vous ne copiez pas <STRONG>PsExec.exe</STRONG>, l’outil de contrainte de conversation permanente génère une exception d’erreur et ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="b264d-113">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="b264d-114">Assurez-vous que vous respectez ces conditions préalables avant d’exécuter l’outil.</span><span class="sxs-lookup"><span data-stu-id="b264d-114">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="b264d-115">Pour plus d’informations sur l’installation de <STRONG>PsExec.exe</STRONG>, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .</span><span class="sxs-lookup"><span data-stu-id="b264d-115">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="b264d-116">Environnements pris en charge</span><span class="sxs-lookup"><span data-stu-id="b264d-116">Supported Environments</span></span>

<span data-ttu-id="b264d-117">Pour des performances optimales, les outils du kit de ressources Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications que celles requises pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b264d-117">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="b264d-118">Vue d’ensemble des outils du kit de ressources</span><span class="sxs-lookup"><span data-stu-id="b264d-118">Resource Kit Tools Overview</span></span>

<span data-ttu-id="b264d-119">Voici les outils fournis dans le kit de ressources de conversation permanente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b264d-119">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="b264d-120">La section suivante fournit une description de chaque outil, notamment les exigences et l’utilisation de l’exemple.</span><span class="sxs-lookup"><span data-stu-id="b264d-120">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="b264d-121">AffCheck</span><span class="sxs-lookup"><span data-stu-id="b264d-121">AffCheck</span></span>

  - <span data-ttu-id="b264d-122">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="b264d-122">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="b264d-123">Outil ChatStress</span><span class="sxs-lookup"><span data-stu-id="b264d-123">ChatStress Tool</span></span>

  - <span data-ttu-id="b264d-124">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="b264d-124">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="b264d-125">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="b264d-125">ChatUsageReport</span></span>

  - <span data-ttu-id="b264d-126">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="b264d-126">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="b264d-127">AffCheck</span><span class="sxs-lookup"><span data-stu-id="b264d-127">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b264d-128">Description</span><span class="sxs-lookup"><span data-stu-id="b264d-128">Description</span></span>

<span data-ttu-id="b264d-129">L’outil AffCheck confirme que les enregistrements d’appartenance au groupe et à l’utilisateur de la base de données principale de conversation permanente correspondent à ceux des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b264d-129">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b264d-130">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b264d-130">Requirements</span></span>

<span data-ttu-id="b264d-131">L’outil est installé avec le programme d’installation PersistentChatResKit sur un ordinateur joint à un domaine.</span><span class="sxs-lookup"><span data-stu-id="b264d-131">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="b264d-132">Le compte d’utilisateur sous lequel l’outil est exécuté doit disposer d’un accès en lecture à la base de données principale de conversation permanente et aux services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b264d-132">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="b264d-133">Utilisation</span><span class="sxs-lookup"><span data-stu-id="b264d-133">Usage</span></span>

<span data-ttu-id="b264d-134">Configurez le fichier AffCheck.exe.config conformément aux instructions du fichier de configuration et exécutez l’outil AffCheck sans paramètres de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="b264d-134">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="b264d-135">Voici le contenu de la AffCheck.exe.config par défaut.</span><span class="sxs-lookup"><span data-stu-id="b264d-135">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="b264d-136">**AffCheck.exe.config :**</span><span class="sxs-lookup"><span data-stu-id="b264d-136">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="b264d-137">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="b264d-137">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b264d-138">Description</span><span class="sxs-lookup"><span data-stu-id="b264d-138">Description</span></span>

<span data-ttu-id="b264d-139">L’outil PersistentChatMonitoringSummary déplace les informations de surveillance de conversation permanente de la base de données de surveillance dans un fichier CSV spécifié.</span><span class="sxs-lookup"><span data-stu-id="b264d-139">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="b264d-140">Le fichier CSV contiendra une répartition des sessions de conversation permanente en nombre total de sessions, de sessions réussies, d’échecs inattendus, d’échecs attendus et de la répartition des échecs inattendus par ID de diagnostic, le nombre de défaillances et la description de l’échec.</span><span class="sxs-lookup"><span data-stu-id="b264d-140">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b264d-141">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b264d-141">Requirements</span></span>

<span data-ttu-id="b264d-142">Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès à la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b264d-142">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="b264d-143">Le compte d’utilisateur sous lequel l’outil s’exécute doit disposer d’un accès en lecture à la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b264d-143">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="b264d-144">Le fichier, PersistentChatMonitoringSummary.exe.config, doit contenir une \<connectionStrings\> section qui définit la chaîne de connexion à la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b264d-144">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="b264d-145">Il doit également contenir une clé pour le PersistentChatEndpointUri pour lequel les données de surveillance seront collectées, et un chemin d’accès de fichier vers un emplacement pour le fichier CSV qui sera généré.</span><span class="sxs-lookup"><span data-stu-id="b264d-145">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="b264d-146">Reportez-vous au fichier de configuration installé pour obtenir des exemples.</span><span class="sxs-lookup"><span data-stu-id="b264d-146">Refer to the installed config file for examples.</span></span> <span data-ttu-id="b264d-147">Le fichier doit se trouver dans le même répertoire que l’outil.</span><span class="sxs-lookup"><span data-stu-id="b264d-147">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="b264d-148">Utilisation</span><span class="sxs-lookup"><span data-stu-id="b264d-148">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="b264d-149">Ces paramètres définissent la sélection de données :</span><span class="sxs-lookup"><span data-stu-id="b264d-149">These parameters define the selection of data:</span></span>

<span data-ttu-id="b264d-150">**StartDateTime :** Spécifie éventuellement la date de début de la période de sélection.</span><span class="sxs-lookup"><span data-stu-id="b264d-150">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="b264d-151">Valeur par défaut : 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="b264d-151">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="b264d-152">**EndDateTime :** Spécifie éventuellement la dernière date de la période de sélection.</span><span class="sxs-lookup"><span data-stu-id="b264d-152">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="b264d-153">Valeur par défaut : maintenant</span><span class="sxs-lookup"><span data-stu-id="b264d-153">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="b264d-154">Exemple</span><span class="sxs-lookup"><span data-stu-id="b264d-154">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="b264d-155">Outil de contrainte de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b264d-155">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b264d-156">Description</span><span class="sxs-lookup"><span data-stu-id="b264d-156">Description</span></span>

<span data-ttu-id="b264d-157">L’outil de contrainte de conversation permanente offre un moyen simple de simuler l’utilisation de la conversation permanente pour tester les performances du monde réel, y compris les modèles utilisateur variés afin de mieux répondre aux scénarios d’utilisation attendus.</span><span class="sxs-lookup"><span data-stu-id="b264d-157">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b264d-158">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b264d-158">Requirements</span></span>

<span data-ttu-id="b264d-159">Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-159">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="b264d-160">En plus de cet ordinateur *contrôleur* , vous aurez besoin de plusieurs machines de *chargeur* .</span><span class="sxs-lookup"><span data-stu-id="b264d-160">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="b264d-161">Pour tous les 10 000 utilisateurs de votre modèle utilisateur, vous aurez besoin d’au moins 4 Go de RAM libre sur un ordinateur chargeur.</span><span class="sxs-lookup"><span data-stu-id="b264d-161">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="b264d-162">Par exemple, une exécution avec des utilisateurs de 80K nécessite environ 32 Go de RAM répartis sur tous les ordinateurs de chargement.</span><span class="sxs-lookup"><span data-stu-id="b264d-162">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="b264d-163">Nous vous recommandons d’avoir au moins trois machines de chargeur, quelle que soit la charge attendue.</span><span class="sxs-lookup"><span data-stu-id="b264d-163">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="b264d-164">Les machines de chargeur doivent disposer de l’infrastructure .NET 4,5 et de la version redistribuable de Visual C++ 2012.</span><span class="sxs-lookup"><span data-stu-id="b264d-164">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="b264d-165">Configuration</span><span class="sxs-lookup"><span data-stu-id="b264d-165">Configuration</span></span>

<span data-ttu-id="b264d-166">Copiez les fichiers ChatStressTool dans un dossier partagé accessible à partir de tous les ordinateurs de chargement.</span><span class="sxs-lookup"><span data-stu-id="b264d-166">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="b264d-167">Créez des utilisateurs et des canaux à utiliser dans l’exécution de contrainte :</span><span class="sxs-lookup"><span data-stu-id="b264d-167">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="b264d-168">Créez autant d’utilisateurs que vous appelez votre modèle utilisateur, activez-les pour Lync et définissez leur stratégie de conversation permanente sur activé.</span><span class="sxs-lookup"><span data-stu-id="b264d-168">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="b264d-169">Créez une catégorie pour vos canaux de stress, puis créez autant de salles que nécessaire sous cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="b264d-169">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="b264d-170">La catégorie doit avoir tous les utilisateurs de stress dans sa liste **autorisée** (par le biais de l’ajout de leur unité d’organisation) et les salles de stress doivent avoir le paramètre de confidentialité « **ouvert**».</span><span class="sxs-lookup"><span data-stu-id="b264d-170">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="b264d-171">Nous vous recommandons de créer des salles de contrainte supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b264d-171">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="b264d-172">Vous pouvez créer 50 000 salles à l’aide de la commande d’interface de ligne de commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="b264d-172">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="b264d-173">Modifiez les fichiers de configuration pour qu’ils s’ajustent à votre topologie :</span><span class="sxs-lookup"><span data-stu-id="b264d-173">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="b264d-174">Dans **LoaderProcess.exe.config**, remplacez « Controller.contoso.com » par le nom de domaine complet (FQDN) de l’ordinateur contrôleur.</span><span class="sxs-lookup"><span data-stu-id="b264d-174">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="b264d-175">Dans **StressLauncher.exe.config :**</span><span class="sxs-lookup"><span data-stu-id="b264d-175">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="b264d-176">Remplacez la valeur du paramètre « LoaderBinary » par le chemin d’accès du dossier partagé.</span><span class="sxs-lookup"><span data-stu-id="b264d-176">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="b264d-177">Remplacez « AdminUser »/« AdminPassword » par les informations d’identification qui disposent d’un accès administrateur aux machines de chargeur.</span><span class="sxs-lookup"><span data-stu-id="b264d-177">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="b264d-178">Remplacez « ChannelCategory » par le nom de la catégorie dans laquelle les canaux de contrainte ont été créés.</span><span class="sxs-lookup"><span data-stu-id="b264d-178">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="b264d-179">Remplacez « UserNamePattern » et « UserPasswordPattern » par un modèle qui correspond aux informations d’identification de votre utilisateur de stress.</span><span class="sxs-lookup"><span data-stu-id="b264d-179">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="b264d-180">{0} est remplacé par le numéro d’index de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b264d-180">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="b264d-181">Remplacez « Domain » par « Domain » par le domaine SIP de votre topologie de test.</span><span class="sxs-lookup"><span data-stu-id="b264d-181">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="b264d-182">Remplacez « ConnectionString » par une chaîne de connexion pour votre base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-182">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="b264d-183">Remplacez « UserIndexStart » par l’index du premier utilisateur à contrainte.</span><span class="sxs-lookup"><span data-stu-id="b264d-183">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="b264d-184">Remplacez « LyncFQDN » par le nom de domaine complet (FQDN) de votre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b264d-184">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="b264d-185">Modifiez la liste « machines » pour inclure les noms de machine de tous les ordinateurs de chargement.</span><span class="sxs-lookup"><span data-stu-id="b264d-185">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="b264d-186">Modifiez le paramètre baseAddress du point de terminaison du service (par défaut, « controller.contoso.com ») sur le nom de domaine complet de votre ordinateur contrôleur.</span><span class="sxs-lookup"><span data-stu-id="b264d-186">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="b264d-187">Utilisation</span><span class="sxs-lookup"><span data-stu-id="b264d-187">Usage</span></span>

<span data-ttu-id="b264d-188">Une fois la configuration terminée, ouvrez StressLauncher.exe sur l’ordinateur contrôleur.</span><span class="sxs-lookup"><span data-stu-id="b264d-188">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="b264d-189">Vous pouvez lancer StressLauncher comme n’importe quel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b264d-189">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="b264d-190">Les informations d’identification sous lesquelles les processus de chargeur démarrent sur les ordinateurs de chargeur doivent être spécifiées dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="b264d-190">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="b264d-191">Vous devez également donner une chaîne de connexion qui dispose d’un accès en lecture à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-191">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="b264d-192">Si cette chaîne de connexion utilise l’authentification Windows intégrée, vous devez lancer StressLauncher en tant qu’utilisateur disposant de cet accès.</span><span class="sxs-lookup"><span data-stu-id="b264d-192">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="b264d-193">Modifiez les paramètres du modèle utilisateur selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b264d-193">Alter the user model settings as needed.</span></span> <span data-ttu-id="b264d-194">Cliquez sur **Démarrer la charge** pour lancer une exécution.</span><span class="sxs-lookup"><span data-stu-id="b264d-194">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="b264d-195">Après une minute ou par conséquent, les utilisateurs commencent à se connecter et la barre de progression commence à se remplir.</span><span class="sxs-lookup"><span data-stu-id="b264d-195">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="b264d-196">À ce stade, vous pouvez peut-être utiliser l’ordinateur contrôleur et prendre des mesures de performances.</span><span class="sxs-lookup"><span data-stu-id="b264d-196">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="b264d-197">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="b264d-197">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b264d-198">Description</span><span class="sxs-lookup"><span data-stu-id="b264d-198">Description</span></span>

<span data-ttu-id="b264d-199">ChatUpgradeVerifier est un outil de comparaison de base de données spécifique à une conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-199">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="b264d-200">L’outil compare la base de données Group chat 2007 R2 ou Group chat 2010 (2007/2010Db) à la base de données de conversation permanente 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="b264d-200">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="b264d-201">L’outil vérifie, une par une, chaque catégorie, la salle de conversation permanente et le complément dans la version 2007/2010Db pour voir s’il apparaît dans le 2013Db.</span><span class="sxs-lookup"><span data-stu-id="b264d-201">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="b264d-202">La comparaison inclut la vérification de tous les paramètres de la catégorie, de la salle de conversation ou du complément, de tous les principaux de l’étendue de la catégorie et de n’importe quel principal d’un rôle sur la catégorie ou la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="b264d-202">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="b264d-203">Si une catégorie ou une salle de conversation ne s’affiche pas correctement dans le 2013Db, les différences seront générées dans un fichier de conflits.</span><span class="sxs-lookup"><span data-stu-id="b264d-203">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="b264d-204">Si, après la mise à niveau, la version 2007/2010Db est modifiée et que cet outil est exécuté, il y aura une différence de sortie dans le fichier de conflits.</span><span class="sxs-lookup"><span data-stu-id="b264d-204">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="b264d-205">Notez que cette application est uniquement un outil de comparaison de bases de données et ne valide pas le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="b264d-205">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b264d-206">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b264d-206">Requirements</span></span>

<span data-ttu-id="b264d-207">Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès aux bases de données principales de conversation permanente (versions précédentes et actuelles pour la conversation permanente).</span><span class="sxs-lookup"><span data-stu-id="b264d-207">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="b264d-208">Le compte d’utilisateur sous lequel l’outil s’exécute doit disposer d’un accès en lecture aux bases de données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-208">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="b264d-209">Le fichier ChatUpgradeVerifier.exe.config doit contenir le paramètre GroupChat2007R2Db ou le paramètre GroupChat2010Db, avec une chaîne de connexion à la base de données de conversation de groupe appropriée (soit groupchat 2007R2, soit 2010).</span><span class="sxs-lookup"><span data-stu-id="b264d-209">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="b264d-210">Elle doit également contenir un paramètre PersistentChat2013Db, avec une chaîne de connexion à la base de données de conversation permanente 2013.</span><span class="sxs-lookup"><span data-stu-id="b264d-210">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="b264d-211">Utilisation</span><span class="sxs-lookup"><span data-stu-id="b264d-211">Usage</span></span>

<span data-ttu-id="b264d-212">Exécutez **ChatUpgradeVerifier** sans aucun paramètre.</span><span class="sxs-lookup"><span data-stu-id="b264d-212">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="b264d-213">Exemple</span><span class="sxs-lookup"><span data-stu-id="b264d-213">Example</span></span>

<span data-ttu-id="b264d-214">![Exécutant ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Exécutant ChatUpgradeVerifier.exe.")</span><span class="sxs-lookup"><span data-stu-id="b264d-214">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="b264d-215">Rapport d’utilisation de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="b264d-215">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b264d-216">Description</span><span class="sxs-lookup"><span data-stu-id="b264d-216">Description</span></span>

<span data-ttu-id="b264d-217">L’outil ChatUsageReport génère un rapport HTML sur l’utilisation du service de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-217">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b264d-218">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b264d-218">Requirements</span></span>

<span data-ttu-id="b264d-219">Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-219">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="b264d-220">Le compte d’utilisateur sous lequel l’outil est exécuté doit disposer d’un accès en lecture à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-220">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="b264d-221">Le fichier, ChatUsageReport.exe.config, doit contenir une \<connectionStrings\> section définissant la chaîne de connexion à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-221">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="b264d-222">Le contenu du fichier de configuration par défaut est inclus ici, à des fins de référence.</span><span class="sxs-lookup"><span data-stu-id="b264d-222">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="b264d-223">Utilisation</span><span class="sxs-lookup"><span data-stu-id="b264d-223">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="b264d-224">Ces paramètres définissent la sélection de données :</span><span class="sxs-lookup"><span data-stu-id="b264d-224">These parameters define the selection of data:</span></span>

<span data-ttu-id="b264d-225">**StartDate :** Spécifie éventuellement la date de début UTC de la période de sélection.</span><span class="sxs-lookup"><span data-stu-id="b264d-225">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="b264d-226">Valeur par défaut : date au plus tôt</span><span class="sxs-lookup"><span data-stu-id="b264d-226">Default: Earliest Date</span></span>

<span data-ttu-id="b264d-227">**EndDate :** Spécifie éventuellement la date de fin UTC de la période de sélection.</span><span class="sxs-lookup"><span data-stu-id="b264d-227">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="b264d-228">Valeur par défaut : maintenant</span><span class="sxs-lookup"><span data-stu-id="b264d-228">Default: Now</span></span>

<span data-ttu-id="b264d-229">Ces paramètres définissent la façon dont les données sont affichées :</span><span class="sxs-lookup"><span data-stu-id="b264d-229">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="b264d-230">**TopActiveUsers :** Si cette option est spécifiée, le rapport inclut les utilisateurs les plus actifs en termes de nombre de messages publiés par l’utilisateur dans la salle de conversation pendant la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-230">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="b264d-231">Par défaut : 10</span><span class="sxs-lookup"><span data-stu-id="b264d-231">Default: 10</span></span>

<span data-ttu-id="b264d-232">**TopActiveRooms :** Si cette option est spécifiée, le rapport inclut les n salles de conversation les plus actives en termes de nombre de messages publiés dans la salle pendant la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-232">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="b264d-233">Par défaut : 10</span><span class="sxs-lookup"><span data-stu-id="b264d-233">Default: 10</span></span>

<span data-ttu-id="b264d-234">**LeastActiveRooms :** Si cette option est spécifiée, le rapport inclut les salles de conversation les moins actives en termes de nombre de messages publiés dans la salle de conversation pendant la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-234">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="b264d-235">Les salles auront au moins un message publié.</span><span class="sxs-lookup"><span data-stu-id="b264d-235">Rooms will have at least one message posted.</span></span> <span data-ttu-id="b264d-236">Par défaut : 10</span><span class="sxs-lookup"><span data-stu-id="b264d-236">Default: 10</span></span>

<span data-ttu-id="b264d-237">**RoomsInactiveSince :** Si cette indication est spécifiée, le rapport inclut une liste des salles de conversation qui ont été inactives depuis la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b264d-237">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="b264d-238">Valeur par défaut : heure entière</span><span class="sxs-lookup"><span data-stu-id="b264d-238">Default: Entire Time</span></span>

<span data-ttu-id="b264d-239">**OutputFolder :** Dossier dans lequel les images ChatUsageReport.html et Graph seront placées.</span><span class="sxs-lookup"><span data-stu-id="b264d-239">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="b264d-240">Il doit être défini dans le fichier de configuration ou dans la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="b264d-240">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="b264d-241">Toutes les valeurs de paramètre de ligne de commande peuvent également être spécifiées dans le fichier ChatUsageReport.exe.config qui se trouve dans le même répertoire que l’outil.</span><span class="sxs-lookup"><span data-stu-id="b264d-241">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="b264d-242">Si une valeur est spécifiée dans le fichier de configuration et la ligne de commande, la valeur de la ligne de commande remplace la valeur du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="b264d-242">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="b264d-243">Output</span><span class="sxs-lookup"><span data-stu-id="b264d-243">Output</span></span>

<span data-ttu-id="b264d-244">Le rapport inclut toujours la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="b264d-244">The report will always include the following output:</span></span>

  - <span data-ttu-id="b264d-245">N premières salles de conversation les plus actives en nombre de publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-245">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="b264d-246">N premiers utilisateurs les plus actifs en nombre de publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-246">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="b264d-247">N premières salles de conversation actives par nombre de publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-247">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="b264d-248">Salles de conversation inactives pendant toute la durée de vie de la base de données ou depuis la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b264d-248">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="b264d-249">Tendance quotidienne des publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-249">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="b264d-250">Tendance hebdomadaire des publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-250">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="b264d-251">Tendance mensuelle des publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-251">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="b264d-252">Total des publications de messages pour la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b264d-252">Total message posts for selected period.</span></span>

  - <span data-ttu-id="b264d-253">Nombre total de salles activées.</span><span class="sxs-lookup"><span data-stu-id="b264d-253">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="b264d-254">Exemple</span><span class="sxs-lookup"><span data-stu-id="b264d-254">Example</span></span>

<span data-ttu-id="b264d-255">L’exemple suivant génère un rapport d’utilisation pour l’année 2001 entière et place l’État dans le OutputFolder spécifié dans la ChatUsageReport.exe.config.</span><span class="sxs-lookup"><span data-stu-id="b264d-255">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="b264d-256">ChatUsageReport.exe.config :</span><span class="sxs-lookup"><span data-stu-id="b264d-256">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="b264d-257">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="b264d-257">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="b264d-258">Description</span><span class="sxs-lookup"><span data-stu-id="b264d-258">Description</span></span>

<span data-ttu-id="b264d-259">ScheduleADSyncForPrincipal est un script Microsoft SQL Server 2012 qui doit être exécuté directement à partir de SQL Server Management Studio lorsqu’il est connecté à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-259">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="b264d-260">Ce script vous permet de forcer la conversation permanente à synchroniser ses enregistrements d’un utilisateur avec ceux des services de domaine Active Directory, au lieu d’attendre la durée de la synchronisation planifiée.</span><span class="sxs-lookup"><span data-stu-id="b264d-260">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="b264d-261">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b264d-261">Requirements</span></span>

<span data-ttu-id="b264d-262">Le compte d’utilisateur sous lequel le script est exécuté doit disposer d’un accès propriétaire à la base de données principale de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="b264d-262">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="b264d-263">Utilisation</span><span class="sxs-lookup"><span data-stu-id="b264d-263">Usage</span></span>

<span data-ttu-id="b264d-264">Voici le contenu du script par défaut :</span><span class="sxs-lookup"><span data-stu-id="b264d-264">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

