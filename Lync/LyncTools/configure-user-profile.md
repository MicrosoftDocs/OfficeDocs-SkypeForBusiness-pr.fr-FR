---
title: Configurer le profil utilisateur
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6615e283e0e426e738cd3cdaf714dd90f57b393e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="100eb-102">Configurer le profil utilisateur</span><span class="sxs-lookup"><span data-stu-id="100eb-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="100eb-103">_**Dernière modification de la rubrique :** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="100eb-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="100eb-104">Les outils inclus dans le package d’outils de contrainte et de performances de Lync Server 2013 vous permettent de créer et de configurer des comptes d’utilisateurs test que vous pouvez utiliser pour exécuter des simulations de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="100eb-105">Utilisez l’outil de création d’utilisateurs Lync Server 2013 pour créer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="100eb-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="100eb-106">(Pour plus d’informations, consultez la rubrique [créer des utilisateurs et des contacts](create-users-and-contacts.md).) Une fois les utilisateurs créés, configurez les profils utilisateur à l’aide de l’outil de configuration de chargement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="100eb-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="100eb-107">Exécution de l’outil de configuration de chargement Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="100eb-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="100eb-108">Pour configurer les profils utilisateur, exécutez l’outil de configuration de chargement (UserProfileGenerator.exe) de Lync Server 2013 et renseignez chacun des onglets.</span><span class="sxs-lookup"><span data-stu-id="100eb-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="100eb-109">UserProfileGenerator.exe génère un répertoire pour chacun des ordinateurs clients dont vous avez besoin pour exécuter la simulation.</span><span class="sxs-lookup"><span data-stu-id="100eb-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="100eb-110">Chaque annuaire client est également fourni avec un script pour démarrer toutes les instances de l’outil de contrainte et performance Lync Server 2013 (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="100eb-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="100eb-111">Les valeurs propres à l’utilisateur spécifiées dans UserProfileGenerator doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateurs Lync Server 2013 (UserProvisioningTool) pour le pool.</span><span class="sxs-lookup"><span data-stu-id="100eb-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="100eb-112">Renseignez les champs de chaque onglet de l’outil de configuration de chargement de Lync Server 2013, comme décrit dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="100eb-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="100eb-113">Configuration commune</span><span class="sxs-lookup"><span data-stu-id="100eb-113">Common Configuration</span></span>

<span data-ttu-id="100eb-114">L’onglet **configuration commune** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="100eb-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="100eb-115">Renseignez les champs de l’onglet **configuration courante** , comme décrit dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="100eb-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="100eb-116">![Onglet Configuration commune.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Onglet Configuration commune.")</span><span class="sxs-lookup"><span data-stu-id="100eb-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="100eb-117">Dans **nombre d’ordinateurs disponibles**, tapez ou cliquez sur le nombre d’ordinateurs que vous souhaitez utiliser pour exécuter LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="100eb-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="100eb-118">Nous vous recommandons de disposer d’un ordinateur pour chaque 4 500 utilisateurs que vous simulerez.</span><span class="sxs-lookup"><span data-stu-id="100eb-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="100eb-119">Ce nombre peut varier si vous réduisez le niveau de charge ou si vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles.</span><span class="sxs-lookup"><span data-stu-id="100eb-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="100eb-120">(Les niveaux de charge sont définis sous l’onglet **scénarios généraux** .)</span><span class="sxs-lookup"><span data-stu-id="100eb-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="100eb-121">Dans **préfixe pour les noms d’utilisateur**, tapez le préfixe du nom d’utilisateur des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="100eb-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="100eb-122">Pour se connecter, l’URI (Uniform Resource Identifier) est : index de \[ démarrage de l’utilisateur UserPrefix... (Nombre d’utilisateurs-1) \] @User domaine.</span><span class="sxs-lookup"><span data-stu-id="100eb-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="100eb-123">Dans **mot de passe pour tous les utilisateurs**, entrez le mot de passe utilisé pour créer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="100eb-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="100eb-124">Si vous laissez ce champ vide, le nom d’utilisateur sera utilisé comme mot de passe.</span><span class="sxs-lookup"><span data-stu-id="100eb-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="100eb-125">Dans **index de démarrage**de l’utilisateur, cliquez sur ou tapez l’index du premier utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="100eb-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="100eb-126">Vous pouvez configurer des plages différentes pour différents types ou niveaux de charge, mais vous devez exécuter UserProfileGenerator.exe une fois par plage que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="100eb-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="100eb-127">Dans **nombre d’utilisateurs**, cliquez sur ou tapez le nombre total d’utilisateurs que vous allez configurer.</span><span class="sxs-lookup"><span data-stu-id="100eb-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="100eb-128">Dans **domaine**de l’utilisateur, tapez le domaine utilisé pour l’URI SIP.</span><span class="sxs-lookup"><span data-stu-id="100eb-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="100eb-129">Il est utilisé pour construire l’URI SIP de chaque utilisateur afin de se connecter au serveur frontal Lync Server 2013 ou au serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="100eb-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="100eb-130">Il peut être différent du domaine de compte.</span><span class="sxs-lookup"><span data-stu-id="100eb-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="100eb-131">Dans **domaine de compte**, tapez connexion au domaine des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="100eb-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="100eb-132">Entrez le nombre maximal de points de terminaison simultanés dans **se connecter par seconde (par instance)** pour lesquels l’outil doit se connecter à tous les points de terminaison/utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="100eb-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="100eb-133">Le taux recommandé est \< = 2 par seconde/standard SKU Fe.</span><span class="sxs-lookup"><span data-stu-id="100eb-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="100eb-134">Dans le proxy d’accès ou le nom de **domaine complet du pool**, tapez le nom de domaine complet (FQDN) du serveur auquel vous souhaitez que les clients se connectent.</span><span class="sxs-lookup"><span data-stu-id="100eb-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="100eb-135">Si les utilisateurs se connectent en externe, spécifiez le proxy d’accès.</span><span class="sxs-lookup"><span data-stu-id="100eb-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="100eb-136">Si les utilisateurs sont internes, spécifiez le nom de domaine complet (FQDN) de leur pool ou serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="100eb-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="100eb-137">Dans **port**, cliquez ou tapez le port que les utilisateurs doivent utiliser pour SIP (la valeur par défaut est 5061).</span><span class="sxs-lookup"><span data-stu-id="100eb-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="100eb-138">Pour les paramètres de serveur réseau externe, spécifiez le **nom de domaine complet du pool ou du proxy d’accès** et le **port**.</span><span class="sxs-lookup"><span data-stu-id="100eb-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="100eb-139">Ces paramètres ne sont utilisés que pour la simulation de charge de point de terminaison externe.</span><span class="sxs-lookup"><span data-stu-id="100eb-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="100eb-140">Scénarios généraux</span><span class="sxs-lookup"><span data-stu-id="100eb-140">General Scenarios</span></span>

<span data-ttu-id="100eb-141">L’onglet **scénarios généraux** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="100eb-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="100eb-142">Configurez les niveaux de charge et les paramètres pour chaque scénario général que vous souhaitez exécuter ou laissez-le désactivé.</span><span class="sxs-lookup"><span data-stu-id="100eb-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="100eb-143">![Onglet scénarios généraux.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Onglet scénarios généraux.")</span><span class="sxs-lookup"><span data-stu-id="100eb-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="100eb-144">Dans la **messagerie instantanée**, qui inclut peer-to-peer et Conferencing, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="100eb-145">Les valeurs de niveau de charge pour tous les champs (à l’exception des services d’informations sur les emplacements) sont <STRONG>désactivées</STRONG>, <STRONG>faible</STRONG>, <STRONG>moyenne</STRONG>, <STRONG>haute</STRONG>et <STRONG>personnalisée</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="100eb-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="100eb-146">Lorsque la sélection est faible, moyenne, haute ou personnalisée, des configurations sont générées pour chaque modalité et client.</span><span class="sxs-lookup"><span data-stu-id="100eb-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="100eb-147">La valeur élevée entraîne la génération du nombre maximal de charges prises en charge pour le serveur, moyenne correspond à 60% de la charge et la valeur faible correspond à 30% de la charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="100eb-148">Dans l' **audioconférence**, qui est l’audioconférence uniquement, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="100eb-149">Les appels P2P sont abordés dans la section scénarios vocaux plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="100eb-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="100eb-150">Pour activer MultiView, ouvrez l’onglet **avancé** pour cette modalité.</span><span class="sxs-lookup"><span data-stu-id="100eb-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="100eb-151">Dans **partage d’application**, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="100eb-152">Dans la **collaboration de données**, qui inclut la Conférence de données, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="100eb-153">Dans **expansion**de la liste de distribution, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="100eb-154">Vous devez également cliquer sur le bouton **avancé** , puis renseignez les champs avec les mêmes valeurs que celles configurées dans l’onglet **liste de distribution** de l’outil de création d’utilisateurs Lync Server (UserProvisioningTool.exe).</span><span class="sxs-lookup"><span data-stu-id="100eb-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="100eb-155">Pour plus d’informations sur ces champs, voir [Create Users and contacts](create-users-and-contacts.md) .</span><span class="sxs-lookup"><span data-stu-id="100eb-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="100eb-156">Dans la **requête Web du carnet d'** adresses, qui est le service de recherche de carnet d’adresses (et non le téléchargement du fichier de carnet d’adresses), spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="100eb-157">Pour activer les téléchargements de carnet d’adresses, cliquez sur le bouton **avancé** correspondant, puis définissez **EnableABSDownload** sur true.</span><span class="sxs-lookup"><span data-stu-id="100eb-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="100eb-158">Dans **service Response Group**, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="100eb-159">Vous devez également cliquer sur le bouton **avancé** correspondant, puis spécifier les URI des groupes Response Group que vous avez déjà créés lors de la mise en service des agents de service Response Group.</span><span class="sxs-lookup"><span data-stu-id="100eb-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="100eb-160">Vous devez spécifier au moins un groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="100eb-160">You must specify at least one response group.</span></span> <span data-ttu-id="100eb-161">Utilisez des points-virgules pour séparer plusieurs groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="100eb-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="100eb-162">Mettez à jour RGSUriSuffixStartIndex et RGSUriSuffixEndIndex avec les valeurs réelles.</span><span class="sxs-lookup"><span data-stu-id="100eb-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="100eb-163">Dans **location Information Services**, sélectionnez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="100eb-164">Le niveau de charge pour les services d’informations d’emplacement doit être **activé** ou **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="100eb-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100eb-165">Chacun des scénarios comprend un bouton <STRONG>avancé</STRONG> , ainsi qu’un ensemble de cases à cocher permettant d’activer des variantes des scénarios.</span><span class="sxs-lookup"><span data-stu-id="100eb-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="100eb-166">Les moyens <STRONG>ad-hoc</STRONG> permettent de générer une simulation de conférences qui seront créées pendant l’heure.</span><span class="sxs-lookup"><span data-stu-id="100eb-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="100eb-167">Le <STRONG>grand conf</STRONG> signifie que le scénario de grande conférence sera simulé.</span><span class="sxs-lookup"><span data-stu-id="100eb-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="100eb-168"><STRONG>External</STRONG> signifie également simuler les utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="100eb-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="100eb-169">Ces boutons et cases à cocher permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et rendre la personnalisation possible.</span><span class="sxs-lookup"><span data-stu-id="100eb-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="100eb-170">Pour chaque scénario sous l’onglet <STRONG>général scénarios</STRONG> (à l’exception des services d’informations sur l’emplacement), si la valeur de niveau de charge est <STRONG>personnalisée</STRONG>, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="100eb-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="100eb-171">Le nom du champ diffère, selon le scénario, mais la description du champ indique « NOTE : ce numéro sera utilisé uniquement si Custom est sélectionné dans le menu déroulant. »</span><span class="sxs-lookup"><span data-stu-id="100eb-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="100eb-172">En règle générale, les valeurs <STRONG>élevé</STRONG>, <STRONG>moyen</STRONG>et <STRONG>faible</STRONG> modifient les taux de conversation par modalité en fonction du modèle utilisateur qui est un équilibre de tous les scénarios.</span><span class="sxs-lookup"><span data-stu-id="100eb-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="100eb-173">S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence dans l’utilisation attendue, nous vous recommandons d’utiliser un taux de conversation <STRONG>personnalisé</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="100eb-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="100eb-174">Scénarios vocaux</span><span class="sxs-lookup"><span data-stu-id="100eb-174">Voice Scenarios</span></span>

<span data-ttu-id="100eb-175">L’onglet **scénarios vocaux** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="100eb-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="100eb-176">Utilisez l’onglet **scénarios vocaux** pour configurer tous les scénarios liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="100eb-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="100eb-177">![Onglet scénarios vocaux.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Onglet scénarios vocaux.")</span><span class="sxs-lookup"><span data-stu-id="100eb-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="100eb-178">Dans **VoIP**, cliquez sur le bouton **avancé** , puis fournissez des valeurs pour les champs **PhoneAreaCode** et **LocationProfile** (plan de numérotation).</span><span class="sxs-lookup"><span data-stu-id="100eb-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="100eb-179">Vous devez également spécifier une valeur pour le **niveau de charge**.</span><span class="sxs-lookup"><span data-stu-id="100eb-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="100eb-180">Si le niveau de charge pour les passerelles **VoIP** et **UC/PSTN** est activé, un réseau téléphonique commuté (PSTN) vers un fichier de configuration de communications unifiées (UC) sera toujours généré pour simuler les appels externes.</span><span class="sxs-lookup"><span data-stu-id="100eb-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="100eb-181">Dans **passerelle cu/PSTN**, spécifiez une valeur pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="100eb-182">Si vous sélectionnez un niveau de charge autre que **désactivé**, vous devez fournir une valeur pour le **Code de zone PSTN** en cliquant sur le bouton **Ajouter** sous serveur de médiation et RTC.</span><span class="sxs-lookup"><span data-stu-id="100eb-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="100eb-183">Vérifiez que vous disposez d’un itinéraire configuré pour l’indicatif régional correspondant.</span><span class="sxs-lookup"><span data-stu-id="100eb-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="100eb-184">Vous pouvez utiliser le panneau de configuration Lync Server ou Lync Server Management Shell pour vérifier la configuration de l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="100eb-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="100eb-185">Dans le **service de surveillance de conférence**, spécifiez une valeur pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="100eb-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="100eb-186">La sélection d’un niveau de charge (autre que **désactivé**) active le champ **numéro de téléphone** .</span><span class="sxs-lookup"><span data-stu-id="100eb-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="100eb-187">Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="100eb-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="100eb-188">De plus, cliquez sur le bouton **avancé** , puis spécifiez une valeur pour le champ **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="100eb-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="100eb-189">Dans **service de parcage d’appel**, spécifiez la valeur appropriée pour le **niveau de charge**.</span><span class="sxs-lookup"><span data-stu-id="100eb-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="100eb-190">Dans **serveur de médiation et RTC**, pour chaque serveur de médiation que vous souhaitez utiliser, vous devez disposer d’un simulateur RTC distinct.</span><span class="sxs-lookup"><span data-stu-id="100eb-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="100eb-191">Une fois que vous avez déterminé le client que vous allez utiliser en tant que simulateur, vous devez configurer votre serveur de médiation pour acheminer les appels vers cet ordinateur sur le port de simulateur RTC que vous avez configuré.</span><span class="sxs-lookup"><span data-stu-id="100eb-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="100eb-192">Cliquez sur **Ajouter** pour configurer la valeur du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="100eb-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100eb-193">Chacun des scénarios dispose d’un bouton <STRONG>avancé</STRONG> situé en regard.</span><span class="sxs-lookup"><span data-stu-id="100eb-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="100eb-194">Ces boutons permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et d’activer la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="100eb-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="100eb-195">Pour chaque scénario sous l’onglet <STRONG>scénarios vocaux</STRONG> , si la valeur de <STRONG>niveau de charge</STRONG> est <STRONG>personnalisée</STRONG>, le taux de conversation sera calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="100eb-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="100eb-196">Le nom du champ diffère, selon le scénario, mais la description du champ indique « NOTE : ce numéro sera utilisé uniquement si Custom est sélectionné dans le menu déroulant. »</span><span class="sxs-lookup"><span data-stu-id="100eb-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="100eb-197">Jusqu'</span><span class="sxs-lookup"><span data-stu-id="100eb-197">Reach</span></span>

<span data-ttu-id="100eb-198">La portée est une nouvelle expérience de Lync Server 2013 qui prend en charge les scénarios de conférence via le serveur UCWA (Unified Communications Web API) installé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="100eb-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="100eb-199">L’onglet **atteindre** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="100eb-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="100eb-200">Utilisez l’onglet **atteindre** pour configurer tous les scénarios liés à la portée.</span><span class="sxs-lookup"><span data-stu-id="100eb-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="100eb-201">![Onglet atteindre](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Onglet atteindre")</span><span class="sxs-lookup"><span data-stu-id="100eb-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="100eb-202">Cliquez sur le bouton **avancé** en regard de **paramètres de portée générale**.</span><span class="sxs-lookup"><span data-stu-id="100eb-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="100eb-203">Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool directeur ou sur l’adresse IP virtuelle du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="100eb-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="100eb-204">Dans **partage d’application**, **collaboration de données**et **messagerie instantanée**, sélectionnez la valeur appropriée pour le **niveau de charge**.</span><span class="sxs-lookup"><span data-stu-id="100eb-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100eb-205">Chacun des scénarios dispose d’un bouton <STRONG>avancé</STRONG> situé en regard.</span><span class="sxs-lookup"><span data-stu-id="100eb-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="100eb-206">Ces boutons permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et d’activer la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="100eb-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="100eb-207">Pour chacun des scénarios de portée, si le <STRONG>niveau de charge</STRONG> est <STRONG>Custom</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="100eb-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="100eb-208">Utilisez l’onglet **mobilité** pour configurer tous les scénarios liés à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="100eb-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="100eb-209">![Onglet mobilité.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Onglet mobilité.")</span><span class="sxs-lookup"><span data-stu-id="100eb-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="100eb-210">Cliquez sur le bouton **avancé** en regard de **mobilité (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="100eb-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="100eb-211">Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool directeur ou sur l’adresse IP virtuelle du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="100eb-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="100eb-212">Dans la **présence et l' \\ audio de la messagerie instantanée P2P**, sélectionnez la valeur appropriée pour le **niveau de charge** pour activer la simulation de scénario de mobilité.</span><span class="sxs-lookup"><span data-stu-id="100eb-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="100eb-213">Chacun des scénarios dispose d’un bouton <STRONG>avancé</STRONG> situé en regard.</span><span class="sxs-lookup"><span data-stu-id="100eb-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="100eb-214">Ces boutons permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et d’activer la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="100eb-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="100eb-215">Pour chacun des scénarios de portée, si le <STRONG>niveau de charge</STRONG> est <STRONG>Custom</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="100eb-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="100eb-216">Résumé</span><span class="sxs-lookup"><span data-stu-id="100eb-216">Summary</span></span>

<span data-ttu-id="100eb-217">L’onglet **Résumé** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="100eb-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="100eb-218">![Onglet Résumé.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Onglet Résumé.")</span><span class="sxs-lookup"><span data-stu-id="100eb-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="100eb-219">L’onglet **Résumé** indique les utilisateurs à utiliser pour chacun des scénarios.</span><span class="sxs-lookup"><span data-stu-id="100eb-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="100eb-220">Il est possible de configurer manuellement des plages de numéros d’utilisateur en activant la case à cocher **activer la génération personnalisée** de la plage d’utilisateurs, puis en double-cliquant sur le scénario dans le tableau qui contient la **plage d’utilisateurs** que vous souhaitez personnaliser.</span><span class="sxs-lookup"><span data-stu-id="100eb-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="100eb-221">Vérifiez (RunClient.bat) ajoutez un retard de connexion au démarrage, afin d’inclure des retards dans les fichiers de commandes générés pour correspondre au taux de connexion.</span><span class="sxs-lookup"><span data-stu-id="100eb-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="100eb-222">Ceci est utile pour empêcher la surcharge de serveur lors de la connexion d’un grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="100eb-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="100eb-223">Cliquez sur **générer des fichiers**, puis sélectionnez le dossier où vous souhaitez générer la configuration.</span><span class="sxs-lookup"><span data-stu-id="100eb-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="100eb-224">Une boîte de dialogue semblable à la figure suivante apparaît lorsque les fichiers ont été correctement créés.</span><span class="sxs-lookup"><span data-stu-id="100eb-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="100eb-225">![Accusé de réception de la création de fichiers.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Accusé de réception de la création de fichiers.")</span><span class="sxs-lookup"><span data-stu-id="100eb-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="100eb-226">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="100eb-226">See Also</span></span>


[<span data-ttu-id="100eb-227">Créer des utilisateurs et des contacts</span><span class="sxs-lookup"><span data-stu-id="100eb-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
