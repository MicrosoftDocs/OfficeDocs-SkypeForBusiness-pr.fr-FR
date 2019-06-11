---
title: 'Lync Server 2013: utilisation de Microsoft SQL Server 2008 R2 en tant que base de données System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858134b4d7f2a2fbc4e15c14e121ac12679c9ddc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="fd94f-102">Utilisation de Microsoft SQL Server 2008 R2 en tant que base de données Gestionnaire d’opérations System Center pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd94f-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd94f-103">_**Dernière modification de la rubrique:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="fd94f-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="fd94f-104">Pour utiliser SQL Server 2008 R2 en tant que base de données principale, suivez les étapes décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fd94f-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="fd94f-105">Configuration de SQL Server 2008 R2 et SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fd94f-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="fd94f-106">Avant de commencer à installer System Center Operations Manager, vous devez apporter deux modifications à SQL Server 2008 R2 et à votre configuration SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="fd94f-107">(Ces modifications sont requises uniquement si vous utilisez SQL Server 2008 R2 en tant que base de données Operations Manager.) Tout d’abord, procédez comme suit sur l’ordinateur qui héberge votre base de données Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fd94f-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="fd94f-108">Cliquez sur **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="fd94f-109">Dans la boîte de dialogue **exécuter** , **tapez C\\: Program\\Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting Services\\ReportServer** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="fd94f-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="fd94f-110">Dans le dossier **reportserver** , ouvrez le fichier **RSReportServer. config** dans le bloc-notes ou dans un autre éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="fd94f-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="fd94f-111">Au début du fichier, vous verrez une série de nœuds «ajouter une touche».</span><span class="sxs-lookup"><span data-stu-id="fd94f-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="fd94f-112">Recherchez l’entrée commençant \*\* \<par ajouter Key = «SecureConnectionLevel»\*\* et définissez la valeur sur **0**:</span><span class="sxs-lookup"><span data-stu-id="fd94f-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="fd94f-113">Enregistrez le fichier **RSReportServer. config** , puis fermez votre éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="fd94f-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="fd94f-114">Après avoir effectué la mise à jour du fichier de configuration du serveur de rapports, vous devez affecter le certificat approprié à SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="fd94f-115">Pour cela, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="fd94f-115">To do that:</span></span>

1.  <span data-ttu-id="fd94f-116">Cliquez sur **Démarrer**, **sur tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **outils de configuration**, puis sur gestionnaire de configuration Reporting **services**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="fd94f-117">Dans la boîte de dialogue **connexion de configuration** de Reporting Services, assurez-vous que le nom de votre serveur apparaît dans la zone **nom du serveur** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="fd94f-118">Sélectionnez l’instance de SQL Server qui héberge votre base de données Operations Manager (par exemple, **ARCHINST**) dans la liste déroulante de l' **instance Report Server** , puis cliquez sur **se connecter**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="fd94f-119">Dans le gestionnaire de configuration Reporting Services, cliquez sur **URL du service Web**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="fd94f-120">Dans la page **URL du service Web** , sélectionnez le certificat à utiliser pour la création de rapports services dans la liste déroulante **certificat SSL** , puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="fd94f-121">Après quelques secondes, une paire d’URL est affichée sous **URL du service Web de Report Server**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="fd94f-122">Cliquez sur les deux URL pour vérifier que vous pouvez accéder à SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="fd94f-123">Fermez le gestionnaire de configuration de report services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="fd94f-124">Création d’une base de données System Center Operations Manager à utiliser avec SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fd94f-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="fd94f-125">Si vous voulez configurer System Center Operations Manager de façon à utiliser une base de données SQL Server 2008 R2, vous devez «manuellement» créer la base de données Operations Manager sur l’ordinateur exécutant SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="fd94f-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="fd94f-126">(De nouveau, cette procédure n’est pas nécessaire si vous utilisez SQL Server 2005 ou SQL Server 2008 comme base de données principale.)</span><span class="sxs-lookup"><span data-stu-id="fd94f-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="fd94f-127">Pour créer manuellement une base de données Operations Manager, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="fd94f-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="fd94f-128">Sur le média de configuration de System Center Operations Manager 2007 R2,\\dans le dossier amd64 de SupportTools, double-cliquez sur **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="fd94f-129">Dans l’Assistant Configuration de la base de données, dans la page **Bienvenue dans l’Assistant Configuration de la base de données** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="fd94f-130">Dans la page **informations de la base de données** , conservez tous les paramètres, puis cliquez sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="fd94f-131">Dans la **page Configuration du groupe de gestion** , tapez un nom pour votre groupe d’administration (par exemple, analyse du **serveur Lync**) dans la zone **nom du groupe de gestion** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="fd94f-132">Dans la page **rapports d’erreurs Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="fd94f-133">Dans la page **Résumé** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="fd94f-134">Création d’un entrepôt de données System Center Operations Manager à utiliser avec SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="fd94f-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="fd94f-135">Microsoft Lync Server 2013 est fourni avec trois nouveaux rapports System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="fd94f-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="fd94f-136">**Rapport de disponibilité du scénario de bout en bout**   ce rapport décrit en détail la disponibilité des services principaux de Lync Server tels que l’inscription ou la présence.</span><span class="sxs-lookup"><span data-stu-id="fd94f-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="fd94f-137">**Rapport de capacité**   utilisant des informations de compteurs de performance, ce rapport affiche des tendances pour les composants système tels que la disponibilité de la mémoire et l’utilisation du processeur.</span><span class="sxs-lookup"><span data-stu-id="fd94f-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="fd94f-138">**Rapport de composant**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd94f-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="fd94f-139">Pour pouvoir utiliser ces nouveaux rapports, vous devez installer un Data Warehouse System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fd94f-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="fd94f-140">(Un entrepôt de données fournit un espace de stockage de données opérationnelles longue durée.) Pour utiliser un entrepôt de données avec SQL Server 2008 R2, vous devez effectuer les étapes suivantes sur l’ordinateur qui héberge votre base de données SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fd94f-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="fd94f-141">Sur le média de configuration de System Center Operations Manager,\\dans\\le dossier SupportTools de configuration, double-cliquez sur **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="fd94f-142">Dans l’Assistant Configuration de la base de données, dans la page **Bienvenue dans l’Assistant Configuration de la base de données** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="fd94f-143">Dans la page **informations de la base de** données, sélectionnez **base de données du Data Warehouse Operations Manager** dans la liste déroulante **type de base de données** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="fd94f-144">Dans la page **Résumé** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="fd94f-145">Installation de la console System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="fd94f-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="fd94f-146">La console Operations Manager est l’outil principal utilisé pour gérer System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fd94f-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="fd94f-147">Avant d’installer la console Operations Manager, assurez-vous d’avoir installé une version prise en charge de SQL Server, ainsi que le service SQL Server Reporting.</span><span class="sxs-lookup"><span data-stu-id="fd94f-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="fd94f-148">Il est également recommandé d’exécuter le gestionnaire de configuration Reporting Services de SQL Server pour vérifier que le service de création de rapports est correctement installé et configuré.</span><span class="sxs-lookup"><span data-stu-id="fd94f-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="fd94f-149">Pour installer la console System Center Operations Manager, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="fd94f-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="fd94f-150">Sur le média de configuration de System Center Operations Manager, double-cliquez sur **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="fd94f-151">Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **vérifier les conditions préalables**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="fd94f-152">Dans la visionneuse de logiciels de System Center Operations Manager, sélectionnez les composants System Center à installer: (**serveur**; **Console**; et **PowerShell**), puis cliquez sur **vérifier**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="fd94f-153">Vérifiez qu’aucun problème de blocage n’a été signalé, puis cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="fd94f-154">Si un problème de blocage a été signalé, corrigez le problème, puis cliquez sur **vérifier** pour réexécuter les tests préalables.</span><span class="sxs-lookup"><span data-stu-id="fd94f-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="fd94f-155">Dans le programme d’installation de System Center Operations Manager, cliquez sur **installer Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="fd94f-156">Dans l’Assistant Configuration de System Center Operations Manager, dans la page Bienvenue dans l' **Assistant Configuration de System Center Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="fd94f-157">Sur la page **contrat de licence utilisateur final** , sélectionnez **J’accepte les conditions du contrat de licence** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="fd94f-158">Sur la page **inscription de produit** , tapez votre nom dans la zone nom d' **utilisateur** et le nom de votre organisation dans la zone **organisation** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="fd94f-159">Tapez votre clé de produit System Center Operations Manager dans la zone **Entrez votre clé** de produit à 25 chiffres, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="fd94f-160">Dans la page **configuration personnalisée** , sélectionnez les options du centre de systèmes à installer, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="fd94f-161">Sélectionnez serveur de **gestion**, **interfaces utilisateur**et **console Web** à installer.</span><span class="sxs-lookup"><span data-stu-id="fd94f-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="fd94f-162">La **base de données** ne doit pas être sélectionnée et ne peut pas être installée.</span><span class="sxs-lookup"><span data-stu-id="fd94f-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="fd94f-163">Dans la page d' **instance du serveur de base de données SC** , vérifiez que le nom de l’ordinateur sur lequel les bases de données du gestionnaire d’opérations sont installées apparaît dans la zone **serveur de base de données System Center** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="fd94f-164">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-164">Click **Next**.</span></span>

10. <span data-ttu-id="fd94f-165">Sur la **page compte d’action du serveur de gestion** , sélectionnez **domaine ou compte d’ordinateur local** , puis entrez les valeurs appropriées dans les zones **compte d’utilisateur**, **mot de passe**et **domaine ou ordinateur local** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="fd94f-166">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-166">Click **Next**.</span></span>

11. <span data-ttu-id="fd94f-167">Sur la page du **compte de service SDK et de configuration** , sélectionnez **domaine ou compte d’ordinateur local** , puis entrez les valeurs appropriées dans les zones **compte d’utilisateur**, **mot de passe**et **domaine ou ordinateur local** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="fd94f-168">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-168">Click **Next**.</span></span>

12. <span data-ttu-id="fd94f-169">Dans la page **rapports d’erreurs Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="fd94f-170">Sur la page du **programme d’amélioration** du produit, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="fd94f-171">Dans la page êtes-vous **prêt à installer le programme** , cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="fd94f-172">Dans la page **fin de la procédure de configuration de System Center Operations Manager** , désactivez la clé de chiffrement de **sauvegarde** et **Démarrez les cases à cocher** de la console, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="fd94f-173">Dans le programme d’installation de System Center Operations Manager, cliquez sur **quitter**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="fd94f-174">Installation de System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fd94f-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="fd94f-175">Après l’installation et la configuration de la console System Center Operations Manager, vous devez installer System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="fd94f-176">Si vous utilisez SQL Server 2008 R2 comme base de données principale Operations Manager, cela signifie que vous devez tout d’abord apporter un changement temporaire au groupe de sécurité associé à SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="fd94f-177">Si vous utilisez SQL Server 2008 R2, vous devez effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="fd94f-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="fd94f-178">Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="fd94f-179">Dans le gestionnaire de serveur, développez **configuration**, **utilisateurs et groupes locaux**, puis cliquez sur **groupes**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="fd94f-180">Recherchez le groupe suivant, dans lequel ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance SQL Server de la base de données du centre de données: **SQLServerReportServerUser $ ATL-\_SC-001 $ MSRS10 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="fd94f-181">Cliquez avec le bouton droit sur le groupe \*\*\*\*, puis cliquez sur Renommer.</span><span class="sxs-lookup"><span data-stu-id="fd94f-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="fd94f-182">Renommez le groupe en supprimant \*\* \_50\*\* du nom du groupe.</span><span class="sxs-lookup"><span data-stu-id="fd94f-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="fd94f-183">Par exemple: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="fd94f-184">Fermez le gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="fd94f-184">Close Server Manager.</span></span>

<span data-ttu-id="fd94f-185">À ce stade, vous êtes prêt à installer System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="fd94f-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="fd94f-186">Pour:</span><span class="sxs-lookup"><span data-stu-id="fd94f-186">To do this:</span></span>

1.  <span data-ttu-id="fd94f-187">Sur le média de configuration de System Center Operations Manager 2007 R2, double-cliquez sur **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="fd94f-188">Dans System Center Operations Manager 2007 R2, cliquez sur **installer le rapport Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="fd94f-189">Dans l’Assistant Configuration de création de rapports de System Center Operations Manager 2007 R2, dans la page Bienvenue dans le **programme d’installation de création de rapports Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="fd94f-190">Dans la page **contrat de licence utilisateur final** , sélectionnez **J’accepte les conditions du contrat de licence** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="fd94f-191">Sur la page **inscription de produit** , assurez-vous que votre nom et le nom de votre organisation apparaissent dans les zones nom d' **utilisateur** et **organisation** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="fd94f-192">Dans la page **configuration personnalisée** , cliquez sur **serveur de création de rapports** , sélectionnez **ce composant, et tous les composants dépendants, seront installés sur le lecteur de disque local**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="fd94f-193">Cliquez sur **entrepôt de données** et sélectionnez **ce composant ne sera pas disponible**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="fd94f-194">Dans la page **connexion à un serveur de gestion racine** , tapez le nom de votre serveur de gestion de la racine Operations Manager dans la zone **serveur de gestion racine** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="fd94f-195">Dans la page **se connecter à l’entrepôt de données Operations Manager** , entrez l’instance SQL Server dans laquelle se trouve votre entrepôt de données dans la zone **instance SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="fd94f-196">(Si votre entrepôt de données se trouve dans l’instance par défaut, tapez simplement le nom du serveur, par exemple: ATL-SQL-001.) Vérifiez que le nom de la base de données **OperationsManagerDW** s’affiche dans la zone **nom** et que le port **1433** s’affiche dans la zone **port SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="fd94f-197">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-197">Click **Next**.</span></span>

9.  <span data-ttu-id="fd94f-198">Dans la page d' **instance SQL Server Report** , sélectionnez votre serveur SQL Server Reporting dans la liste déroulante **Enter SQL Server Reporting Services** , puis cliquez sur **Next (suivant**).</span><span class="sxs-lookup"><span data-stu-id="fd94f-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="fd94f-199">Sur la page **compte d’écriture du magasin de données** , entrez le nom et le mot de passe de l’utilisateur auquel vous souhaitez attribuer des autorisations d’écriture dans l’entrepôt de données dans les zones compte d' **utilisateur** et **mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="fd94f-200">Sélectionnez le domaine de l’utilisateur dans la liste déroulante **Domain** , puis cliquez sur **Next (suivant**).</span><span class="sxs-lookup"><span data-stu-id="fd94f-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="fd94f-201">Sur la page **compte du lecteur de données** , entrez le nom et le mot de passe du compte d’utilisateur à utiliser lorsque SQL Reporting Services interroge l’entrepôt de données dans les zones compte d' **utilisateur** et **mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="fd94f-202">Sélectionnez le domaine de compte dans la liste déroulante **Domain** , puis cliquez sur **Next (suivant**).</span><span class="sxs-lookup"><span data-stu-id="fd94f-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="fd94f-203">Dans la page **rapports de données opérationnelles** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="fd94f-204">Sur la page **Microsoft Update** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="fd94f-205">Dans la page êtes-vous **prêt à installer le programme** , cliquez sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="fd94f-206">Dans la page **fin de l’Assistant Installation des composants de création de rapports Operations Manager** , cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="fd94f-207">Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **quitter**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="fd94f-208">Après l’installation de la fonctionnalité de création de rapports du centre de systèmes, vous pouvez utiliser la procédure suivante pour réinitialiser le nom du groupe de sécurité associé à la création de rapports SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd94f-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="fd94f-209">Là encore, cette procédure est requise uniquement si vous utilisez SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fd94f-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="fd94f-210">Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="fd94f-211">Dans le gestionnaire de serveur, développez **configuration**, **utilisateurs et groupes locaux**, puis cliquez sur **groupes**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="fd94f-212">Recherchez le groupe suivant, dans lequel ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance SQL Server pour les bases de données d’archivage et de surveillance: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="fd94f-213">Cliquez avec le bouton droit sur le groupe \*\*\*\*, puis cliquez sur Renommer.</span><span class="sxs-lookup"><span data-stu-id="fd94f-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="fd94f-214">Pour renommer le groupe, ajoutez \*\* \_50\*\* à la fin du nom du groupe, juste avant le nom de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd94f-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="fd94f-215">Par exemple: **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="fd94f-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="fd94f-216">Fermez le gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="fd94f-216">Close Server Manager.</span></span>

<span data-ttu-id="fd94f-217">Si la console opérations de System Center est ouverte, vous devez fermer l’application, puis la redémarrer. dans le cas contraire, l’onglet **création de rapports** n’apparaît pas dans l’interface utilisateur de la console opérations.</span><span class="sxs-lookup"><span data-stu-id="fd94f-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="fd94f-218">Notez que, après le redémarrage de la console d’opérations pour la première fois, tous les rapports d’analyse apparaissent dans l’onglet **rapports** .</span><span class="sxs-lookup"><span data-stu-id="fd94f-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

