---
title: 'Lync Server 2013 : utilisation de Microsoft SQL Server 2008 R2 en tant que base de données System Center Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0001d70033aac6d7c6125bb9e4016143beefc80f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="20da4-102">Utilisation de Microsoft SQL Server 2008 R2 comme base de données System Center Operations Manager pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20da4-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20da4-103">_**Dernière modification de la rubrique :** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="20da4-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="20da4-104">Pour utiliser SQL Server 2008 R2 comme base de données principale, procédez comme indiqué dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="20da4-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="20da4-105">Configuration de SQL Server 2008 R2 et SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="20da4-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="20da4-106">Avant de commencer l’installation de System Center Operations Manager, vous devez effectuer deux modifications à SQL Server 2008 R2 et à votre configuration SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="20da4-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="20da4-107">(Ces modifications ne sont requises que si vous utilisez SQL Server 2008 R2 comme base de données Operations Manager.) Tout d’abord, procédez comme suit sur l’ordinateur qui hébergera votre base de données Operations Manager :</span><span class="sxs-lookup"><span data-stu-id="20da4-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="20da4-108">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="20da4-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="20da4-109">Dans la boîte de dialogue **exécuter** , **tapez C\\: Program\\Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting Services\\ReportServer** , puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="20da4-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="20da4-110">Dans le dossier **ReportServer**, ouvrez le fichier **rsreportserver.config** dans le Bloc-notes ou dans un autre éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="20da4-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="20da4-111">Au début du fichier vous verrez une série de nœuds « Add Key ».</span><span class="sxs-lookup"><span data-stu-id="20da4-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="20da4-112">Recherchez l’entrée qui commence \*\* \<à ajouter Key = "SecureConnectionLevel"\*\* et définissez la valeur sur **0**:</span><span class="sxs-lookup"><span data-stu-id="20da4-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="20da4-113">Enregistrez le fichier **rsreportserver.config** et fermez l’éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="20da4-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="20da4-p103">Une fois que vous avez modifié le fichier de configuration du serveur de rapports, vous devez affecter le certificat correct à SQL Server Reporting Services. Pour cela :</span><span class="sxs-lookup"><span data-stu-id="20da4-p103">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services. To do that:</span></span>

1.  <span data-ttu-id="20da4-116">Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft SQL Server 2008 R2**, sur **outils de configuration**, puis sur gestionnaire de **configuration de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="20da4-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="20da4-117">Dans la boîte de dialogue **Connexion relative à la configuration de Reporting Services**, assurez-vous que le nom du serveur apparaît dans la zone **Nom du serveur**.</span><span class="sxs-lookup"><span data-stu-id="20da4-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="20da4-118">Sélectionnez l’instance SQL Server qui doit héberger votre base de données Operations Manager (par exemple, **ARCHINST**) dans la liste déroulante **instance de serveur de rapports** , puis cliquez sur **se connecter**.</span><span class="sxs-lookup"><span data-stu-id="20da4-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="20da4-119">Dans le Gestionnaire de configuration de Reporting Services, cliquez sur \*\*  URL du service web \*\*.</span><span class="sxs-lookup"><span data-stu-id="20da4-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="20da4-p105">Dans la page **URL du service web**, sélectionnez le certificat à utiliser pour Reporting Services dans la liste déroulante \*\*Certificat SSL \*\*, puis cliquez sur **Appliquer**. Après quelques secondes, deux URL apparaissent sous **URL du service web Report Server**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p105">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**. After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="20da4-122">Cliquez sur les deux URL pour vérifier que vous pouvez accéder à SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="20da4-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="20da4-123">Fermez le Gestionnaire de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="20da4-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="20da4-124">Création d’une base de données System Center Operations Manager pour une utilisation avec SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="20da4-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="20da4-125">Si vous souhaitez configurer System Center Operations Manager pour utiliser une base de données SQL Server 2008 R2, vous devez créer manuellement la base de données Operations Manager sur l’ordinateur qui exécute SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="20da4-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="20da4-126">(Encore une fois, ces étapes ne sont pas nécessaires si vous utilisez SQL Server 2005 ou SQL Server 2008 comme base de données principale).</span><span class="sxs-lookup"><span data-stu-id="20da4-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="20da4-127">Pour créer manuellement une base de données Operations Manager, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="20da4-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="20da4-128">Sur le support d’installation de System Center Operations Manager 2007 R2,\\dans le dossier amd64 SupportTools, double-cliquez sur **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="20da4-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="20da4-129">Dans l’Assistant Configuration de base de données, dans la page **Bienvenue dans l’Assistant Configuration de base de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="20da4-130">Dans la page **Informations sur la base de données**, ne modifiez pas les paramètres et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="20da4-131">Dans la **page Configuration du groupe d’administration** , entrez un nom pour votre groupe d’administration (par exemple, **analyse Lync Server**) dans la zone Nom du groupe d' **administration** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="20da4-132">Dans la page **Rapports d’erreurs Operations Manager**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="20da4-133">Dans la page **Résumé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="20da4-134">Création d’un entrepôt de données System Center Operations Manager pour une utilisation avec SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="20da4-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="20da4-135">Microsoft Lync Server 2013 est livré avec trois nouveaux rapports System Center Operations Manager :</span><span class="sxs-lookup"><span data-stu-id="20da4-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="20da4-136">**Rapport de disponibilité des scénarios de bout en bout**   ce rapport présente la disponibilité/temps de fonctionnement des services Lync Server clés tels que l’inscription ou la présence.</span><span class="sxs-lookup"><span data-stu-id="20da4-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="20da4-137">**Rapport de capacité**   à l’aide des informations des compteurs de performance, ce rapport affiche les tendances des composants système, notamment la disponibilité de la mémoire et l’utilisation du processeur.</span><span class="sxs-lookup"><span data-stu-id="20da4-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="20da4-138">**Rapport de composants**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20da4-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="20da4-139">Pour pouvoir utiliser ces nouveaux rapports, vous devez installer un entrepôt de données System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="20da4-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="20da4-140">(Un Data Warehouse offre un stockage à long terme des données opérationnelles.) Pour utiliser un Data Warehouse avec SQL Server 2008 R2, vous devez effectuer les étapes suivantes sur l’ordinateur qui héberge votre base de données SQL Server :</span><span class="sxs-lookup"><span data-stu-id="20da4-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="20da4-141">Sur le support d’installation de System Center Operations Manager,\\dans\\le dossier amd64 du programme d’installation d’SupportTools, double-cliquez sur **DBCreateWizard. exe**.</span><span class="sxs-lookup"><span data-stu-id="20da4-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="20da4-142">Dans l’Assistant Configuration de base de données, dans la page **Bienvenue dans l’Assistant Configuration de base de données**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="20da4-143">Dans la page **Informations sur la base de données**, sélectionnez **Base de données de magasin de données Operations Manager** dans la liste déroulante **Type de base de données** et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="20da4-144">Dans la page **Résumé**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="20da4-145">Installation de la console System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="20da4-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="20da4-146">La console Operations Manager est l’outil principal utilisé pour gérer System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="20da4-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="20da4-147">Avant d’installer la console Operations Manager, assurez-vous que vous avez installé une version prise en charge de SQL Server avec le service SQL Server Reporting.</span><span class="sxs-lookup"><span data-stu-id="20da4-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="20da4-148">Nous vous recommandons également d’exécuter le Gestionnaire de configuration de Reporting Services de SQL Server pour vérifier que Reporting Services est correctement installé et configuré.</span><span class="sxs-lookup"><span data-stu-id="20da4-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="20da4-149">Pour installer la console System Center Operations Manager, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="20da4-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="20da4-150">Sur le support d’installation de System Center Operations Manager, double-cliquez sur **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="20da4-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="20da4-151">Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **vérifier les conditions préalables**.</span><span class="sxs-lookup"><span data-stu-id="20da4-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="20da4-152">Dans la visionneuse requise de System Center Operations Manager, sélectionnez les composants System Center à installer : (**serveur**; **Console**; et **PowerShell**), puis cliquez sur **vérifier**.</span><span class="sxs-lookup"><span data-stu-id="20da4-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="20da4-153">Vérifiez qu’aucun problème de blocage n’est signalé et cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="20da4-154">Si un problème de blocage est signalé, corrigez-le et cliquez sur **Vérifier** pour exécuter de nouveau le test des conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="20da4-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="20da4-155">Dans le programme d’installation de System Center Operations Manager, cliquez sur **installer Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="20da4-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="20da4-156">Dans l’Assistant Installation de System Center Operations Manager, dans la page **Bienvenue dans l’Assistant Installation de System Center Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="20da4-157">Dans la page **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="20da4-158">Sur la page **inscription du produit** , tapez votre nom dans la zone nom d' **utilisateur** et le nom de votre organisation dans la zone **organisation** .</span><span class="sxs-lookup"><span data-stu-id="20da4-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="20da4-159">Tapez votre clé de produit System Center Operations Manager dans la zone **Entrez votre clé de CD à 25 chiffres** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="20da4-p111">Dans la page **Installation personnalisée**, sélectionnez les options de System Center à installer et cliquez sur **Suivant**. Vous devez sélectionner **Serveur d’administration**, **Interfaces utilisateur** et \*\*Console web \*\* pour installer ces fonctionnalités. Ne sélectionnez pas **Base de données**, car cette fonctionnalité ne doit pas être installée.</span><span class="sxs-lookup"><span data-stu-id="20da4-p111">On the **Custom Setup** page select the System Center options to be installed and then click **Next**. You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed. **Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="20da4-163">Sur la page **de l’instance du serveur de base de données SC** , vérifiez que le nom de l’ordinateur sur lequel les bases de données Operations Manager sont installées apparaît dans la zone **serveur de base de données System Center** .</span><span class="sxs-lookup"><span data-stu-id="20da4-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="20da4-164">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-164">Click **Next**.</span></span>

10. <span data-ttu-id="20da4-p113">Dans la page **Compte d’action du serveur d’administration**, sélectionnez **Compte d’ordinateur de domaine ou local**, puis entrez les valeurs appropriées dans les zones **Compte d’utilisateur**, **Mot de passe** et **Ordinateur local ou du domaine**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p113">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

11. <span data-ttu-id="20da4-p114">Dans la page **SDK et compte de service de configuration**, sélectionnez **Compte d’ordinateur de domaine ou local**, puis entrez les valeurs appropriées dans les zones **Compte d’utilisateur**, **Mot de passe** et **Ordinateur local ou du domaine**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p114">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

12. <span data-ttu-id="20da4-169">Dans la page **Rapports d’erreurs Operations Manager**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="20da4-170">Dans la page **Programme d’amélioration du produit**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="20da4-171">Dans la page **Prêt à installer le programme**, cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="20da4-172">Dans la page **Fin de l’Assistant Installation de System Center - Operations Manager**, désactivez les cases à cocher **Sauvegarder la clé de chiffrement** et **Démarrer la console**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="20da4-173">Dans le programme d’installation de System Center Operations Manager, cliquez sur **quitter**.</span><span class="sxs-lookup"><span data-stu-id="20da4-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="20da4-174">Installation de System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="20da4-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="20da4-175">Après l’installation et la configuration de la console System Center Operations Manager, vous devez installer System Center Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="20da4-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="20da4-176">Si vous utilisez SQL Server 2008 R2 comme base de données principale Operations Manager, cela signifie que vous devez d’abord modifier temporairement le groupe de sécurité associé à SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="20da4-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="20da4-177">Si vous utilisez SQL Server 2008 R2, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="20da4-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="20da4-178">Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="20da4-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="20da4-179">Dans le Gestionnaire de serveur, développez **Configuration** et **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.</span><span class="sxs-lookup"><span data-stu-id="20da4-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="20da4-180">Recherchez le groupe suivant, où ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance de SQL Server pour la base de données System Center : **SQLServerReportServerUser $ ATL-SC-\_001 $ MSRS10 50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="20da4-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="20da4-181">Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="20da4-182">Renommez le groupe en supprimant \*\* \_50\*\* du nom du groupe.</span><span class="sxs-lookup"><span data-stu-id="20da4-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="20da4-183">Par exemple : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="20da4-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="20da4-184">Fermez le Gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="20da4-184">Close Server Manager.</span></span>

<span data-ttu-id="20da4-p117">À ce stade, vous êtes prêt à installer System Center Reporting Services. Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="20da4-p117">At this point you are ready to install System Center Reporting Services. To do this:</span></span>

1.  <span data-ttu-id="20da4-187">Sur le support d’installation de System Center Operations Manager 2007 R2, double-cliquez sur **SetupOM. exe**.</span><span class="sxs-lookup"><span data-stu-id="20da4-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="20da4-188">Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **installer la création de rapports d’Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="20da4-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="20da4-189">Dans l’Assistant Configuration de création de rapports de System Center Operations Manager 2007 R2, sur la page Bienvenue dans le **programme d’installation des rapports Operations Manager** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="20da4-190">Dans la page **Contrat de Licence Utilisateur Final**, sélectionnez **J’accepte les termes du contrat de licence**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="20da4-191">Dans la page **Inscription du produit**, assurez-vous que votre nom et celui de votre organisation apparaissent dans les zones **Nom de l’utilisateur** et **Organisation**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="20da4-p118">Dans la page **Installation personnalisée**, cliquez sur **Serveur de rapports** et sélectionnez **Ce composant et tous les composants associés seront installés sur le disque local.**. Cliquez sur **Entrepôt de données**, sélectionnez **Ce composant ne sera pas disponible.**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p118">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**. Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="20da4-194">Dans la page **Connexion au serveur d’administration principal**, tapez le nom du serveur d’administration racine Operations Manager dans la zone **Serveur d’administration racine**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="20da4-p119">Dans la page **Se connecter à l’entrepôt de données d’Operations Manager**, tapez l’instance SQL Server dans laquelle se trouve l’entrepôt de données dans la zone **Instance SQL Server**. (Si l’entrepôt de données se trouve dans l’instance par défaut, tapez simplement le nom du serveur, par exemple : atl-sql-001.) Vérifiez que le nom de la base de données **OperationsManagerDW** apparaît dans la zone **Nom** et que le port **1433** apparaît dans la zone **Port du serveur SQL**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p119">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box. (If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box. Click **Next**.</span></span>

9.  <span data-ttu-id="20da4-198">Dans la page **Instance SQL Server Reporting**, sélectionnez le serveur de rapports SQL Server dans la liste déroulante **Entrez le nom du serveur SQL Server Reporting Services.** et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="20da4-p120">Dans la page **Compte d’écriture d’entrepôt de données**, entrez le nom et le mot de passe de l’utilisateur, auquel des autorisations d’accès en écriture à l’entrepôt de données devront être accordées, dans les zones **Compte d’utilisateur** et **Mot de passe**. Sélectionnez le domaine de l’utilisateur dans la liste déroulante **Domaine** et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p120">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes. Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="20da4-p121">Dans la page **Compte de lecteur de données**, entrez le nom et le mot de passe du compte d’utilisateur à utiliser lorsque SQL Reporting Services interroge l’entrepôt de données dans les zones **Compte d’utilisateur** et **Mot de passe**. Sélectionnez le domaine du compte dans la liste déroulante **Domaine** et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-p121">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes. Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="20da4-203">Dans la page **Rapports de données opérationnelles**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="20da4-204">Dans la page **Microsoft Update**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="20da4-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="20da4-205">Dans la page **Prêt à installer le programme**, cliquez sur **Installer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="20da4-206">Dans la page **Fin de l’Assistant Installation des composants d’Operations Manager Reporting**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="20da4-207">Dans le programme d’installation de System Center Operations Manager 2007 R2, cliquez sur **quitter**.</span><span class="sxs-lookup"><span data-stu-id="20da4-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="20da4-208">Une fois que System Center Reporting a été installé, vous utilisez la procédure suivante pour réinitialiser le nom du groupe de sécurité associé à SQL Server Reporting.</span><span class="sxs-lookup"><span data-stu-id="20da4-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="20da4-209">Cette procédure n’est nécessaire que si vous utilisez SQL Server :</span><span class="sxs-lookup"><span data-stu-id="20da4-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="20da4-210">Cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestionnaire de serveur**.</span><span class="sxs-lookup"><span data-stu-id="20da4-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="20da4-211">Dans le Gestionnaire de serveur, développez **Configuration** et **Utilisateurs et groupes locaux**, puis cliquez sur **Groupes**.</span><span class="sxs-lookup"><span data-stu-id="20da4-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="20da4-212">Recherchez le groupe suivant, où ATL-SC-001 représente le nom de votre ordinateur et ARCHINST représente l’instance de SQL Server pour les bases de données d’archivage et de surveillance : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="20da4-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="20da4-213">Cliquez avec le bouton droit sur le groupe, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="20da4-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="20da4-214">Renommez le groupe en ajoutant \*\* \_50\*\* à la fin du nom du groupe, juste avant le nom de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20da4-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="20da4-215">Par exemple : **SQLServerReportServerUser $ ATL-SC-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="20da4-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="20da4-216">Fermez le Gestionnaire de serveur.</span><span class="sxs-lookup"><span data-stu-id="20da4-216">Close Server Manager.</span></span>

<span data-ttu-id="20da4-p124">Si la console de System Center Operations est ouverte vous devez fermer l’application et la redémarrer. Autrement, l’onglet **Rapports** n’apparaîtra pas dans l’interface utilisateur de la console. Notez qu’après le redémarrage de la console Operations, l’affichage des rapports de surveillance sous l’onglet **Rapports** peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="20da4-p124">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface. Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

