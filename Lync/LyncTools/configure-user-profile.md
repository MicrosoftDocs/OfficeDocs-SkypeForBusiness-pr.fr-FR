---
title: Configurer un profil utilisateur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="4b9a3-102">Configurer un profil utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b9a3-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9a3-103">_**Dernière modification de la rubrique :** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="4b9a3-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="4b9a3-104">Les outils inclus dans le package d’outils de stress et de performance de Lync Server 2013 vous permettent de créer et de configurer des comptes d’utilisateurs test que vous pouvez utiliser pour effectuer des simulations de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="4b9a3-105">Utilisez l’outil de création d’utilisateurs de Lync Server 2013 pour créer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="4b9a3-106">(Pour plus d’informations, consultez [créer des utilisateurs et des contacts](create-users-and-contacts.md).) Une fois les utilisateurs créés, configurez les profils utilisateur à l’aide de l’outil de configuration de chargement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="4b9a3-107">Exécution de l’outil de configuration de chargement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b9a3-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="4b9a3-108">Pour configurer les profils utilisateur, exécutez l’outil de configuration de chargement de Lync Server 2013 (UserProfileGenerator. exe), puis remplissez chacun des onglets.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="4b9a3-109">UserProfileGenerator. exe génère un répertoire pour chaque ordinateur client dont vous avez besoin pour exécuter la simulation.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="4b9a3-110">Chaque répertoire client est également fourni avec un script permettant de démarrer toutes les instances de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="4b9a3-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4b9a3-111">Les valeurs spécifiques à l’utilisateur spécifiées dans UserProfileGenerator doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateurs de Lync Server 2013 (UserProvisioningTool) pour le pool.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="4b9a3-112">Renseignez les champs de chaque onglet de l’outil de configuration de chargement de Lync Server 2013, comme décrit dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="4b9a3-113">Configuration courante</span><span class="sxs-lookup"><span data-stu-id="4b9a3-113">Common Configuration</span></span>

<span data-ttu-id="4b9a3-114">L’onglet **configuration commune** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="4b9a3-115">Remplissez les champs de l’onglet **configuration courante** , comme décrit dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="4b9a3-116">![Onglet Configuration commune.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Onglet Configuration commune.")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="4b9a3-117">Dans **nombre d’ordinateurs disponibles**, tapez ou cliquez sur le nombre d’ordinateurs que vous voulez utiliser pour exécuter LyncPerfTool. exe.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="4b9a3-118">Nous vous recommandons d’avoir un ordinateur pour tous les utilisateurs de 4 500 que vous allez simuler.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="4b9a3-119">Ce nombre peut varier si vous réduisez le niveau de charge ou si vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="4b9a3-120">(Les niveaux de charge sont définis sous l’onglet **scénarios généraux** .)</span><span class="sxs-lookup"><span data-stu-id="4b9a3-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="4b9a3-121">Dans **préfixe pour noms d’utilisateur**, tapez le préfixe correspondant au nom d’utilisateur des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="4b9a3-122">Pour vous connecter, il s’agit de l’URI (Uniform Resource Identifier)\[: UserPrefix de début de l’utilisateur... (Nombre d’utilisateurs-1) \]@User domaine.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="4b9a3-123">Dans **mot de passe pour tous les utilisateurs**, entrez le mot de passe utilisé pour créer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="4b9a3-124">Si vous laissez ce champ vide, le nom d’utilisateur sera utilisé comme mot de passe.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="4b9a3-125">Dans **index de début**de l’utilisateur, cliquez ou tapez l’index du premier utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="4b9a3-126">Vous pouvez configurer différentes plages pour différents types ou niveaux de charge, mais vous devez exécuter UserProfileGenerator. exe une seule fois par la plage que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="4b9a3-127">Dans **nombre d’utilisateurs**, cliquez ou tapez le nombre total d’utilisateurs que vous allez configurer.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="4b9a3-128">Dans **domaine**de l’utilisateur, tapez le domaine utilisé pour l’URI SIP.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="4b9a3-129">Il est utilisé pour créer l’URI SIP de chaque utilisateur pour se connecter au serveur frontal Lync Server 2013 ou Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="4b9a3-130">Il peut être différent du domaine du compte.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="4b9a3-131">Dans **domaine de compte**, tapez la connexion au domaine AD FS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="4b9a3-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="4b9a3-132">Entrez le nombre maximal de points de terminaison concurrents en **se connectant par seconde (par instance)** pour lesquels vous voulez que l’outil se connecte à tous les points de terminaison/utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="4b9a3-133">Le taux recommandé est \<= 2 par seconde/standard PT.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="4b9a3-134">Dans **proxy d’accès ou nom de domaine complet du pool**, tapez le nom de domaine complet (FQDN) du serveur auquel vous souhaitez que les clients se connectent.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="4b9a3-135">Si les utilisateurs se connectent en externe, spécifiez le proxy d’accès.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="4b9a3-136">Si les utilisateurs sont internes, spécifiez le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="4b9a3-137">Dans **port**, cliquez ou tapez le port que les utilisateurs utiliseront pour SIP (la valeur par défaut est 5061).</span><span class="sxs-lookup"><span data-stu-id="4b9a3-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="4b9a3-138">Pour les paramètres de serveur de réseau externe, spécifiez le **nom de domaine complet du proxy ou du pool d’accès** et le **port**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="4b9a3-139">Ces paramètres sont utilisés uniquement pour la simulation de charge de points de terminaison externes.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="4b9a3-140">Scénarios généraux</span><span class="sxs-lookup"><span data-stu-id="4b9a3-140">General Scenarios</span></span>

<span data-ttu-id="4b9a3-141">L’onglet **scénarios généraux** de l’outil de configuration de chargement de Lync Server 2013 est présenté dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="4b9a3-142">Configurez les niveaux de charge et les paramètres pour chacun des scénarios généraux que vous souhaitez exécuter, ou laissez-le désactivé.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="4b9a3-143">![Onglet scénarios généraux.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Onglet scénarios généraux.")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="4b9a3-144">Dans la **messagerie instantanée**, qui inclut les services d’égal à égal et de conférence, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b9a3-145">Les valeurs de niveau de charge de tous les champs (à l’exception des services d’informations de lieu) sont <STRONG>désactivées</STRONG>, <STRONG>faible</STRONG>, <STRONG>moyenne</STRONG>, <STRONG>haute</STRONG>et <STRONG>personnalisée</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="4b9a3-146">Lorsque les valeurs faible, moyenne, haute ou personnalisée sont sélectionnées, des configurations sont générées pour chaque modalité et chaque client.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="4b9a3-147">Élevé entraîne la génération de la valeur maximale prise en charge pour le serveur, moyenne correspond à 60% du chargement et la valeur basse correspond à 30% du chargement.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="4b9a3-148">Dans **audioconférence**, qui est le niveau de conférences audio uniquement, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="4b9a3-149">Les appels d’égal à égal sont abordés dans la section scénarios vocaux, plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="4b9a3-150">Pour activer multivue, ouvrez l’onglet **avancé** pour cette modalité.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="4b9a3-151">Dans **partage d’application**, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="4b9a3-152">Dans la **collaboration de données**, qui inclut les conférences de données, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="4b9a3-153">Dans **extension**de la liste de distribution, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="4b9a3-154">Vous devez également cliquer sur le bouton **avancé** , puis renseigner les champs avec les mêmes valeurs que celles configurées sous l’onglet **liste de distribution** de l’outil de création d’utilisateurs de Lync Server (UserProvisioningTool. exe).</span><span class="sxs-lookup"><span data-stu-id="4b9a3-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="4b9a3-155">Pour plus d’informations sur ces champs, voir [créer des utilisateurs et des contacts](create-users-and-contacts.md) .</span><span class="sxs-lookup"><span data-stu-id="4b9a3-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="4b9a3-156">Dans la **requête Web du carnet d'** adresses, qui est le service de recherche dans le carnet d’adresses (et non le téléchargement du fichier du carnet d’adresses), spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="4b9a3-157">Pour activer les téléchargements du carnet d’adresses, cliquez sur le bouton **avancé** correspondant, puis affectez à **EnableABSDownload** la valeur true.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="4b9a3-158">Dans **service Response Group**, spécifiez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="4b9a3-159">Vous devez également cliquer sur le bouton **avancé** correspondant, puis spécifier les URI des groupes de réponse que vous avez déjà créés lors de la mise en service des agents de groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="4b9a3-160">Vous devez spécifier au moins un groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-160">You must specify at least one response group.</span></span> <span data-ttu-id="4b9a3-161">Utilisez des points-virgules pour séparer plusieurs groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="4b9a3-162">Mettez à jour RGSUriSuffixStartIndex et RGSUriSuffixEndIndex sur les valeurs réelles.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="4b9a3-163">Dans **services d’information d’emplacement**, sélectionnez la valeur appropriée pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="4b9a3-164">Le niveau de charge des services d’information d’emplacement doit être **activé** ou **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b9a3-165">Chacun des scénarios est associé à un bouton <STRONG>avancé</STRONG> qui s’affiche à côté de celui-ci, ainsi qu’un ensemble de cases à cocher permettant de définir des variations des scénarios.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="4b9a3-166">Moyens <STRONG>ad-hoc</STRONG> pour générer une simulation de conférences qui seront créées tout au long de l’heure.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="4b9a3-167">L’environnement de <STRONG>grande taille</STRONG> signifie que le scénario de conférence sera simulé.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="4b9a3-168"><STRONG>Externe</STRONG> signifie également simuler des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="4b9a3-169">Ces boutons et cases à cocher autorisent l’accès à des valeurs propres à chaque scénario, qui modifient le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool) et permettent la personnalisation possible.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="4b9a3-170">Pour chaque scénario sous l’onglet <STRONG>scénarios généraux</STRONG> (à l’exception de services d’information d’emplacement), si la valeur de niveau de charge est <STRONG>personnalisé</STRONG>, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4b9a3-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="4b9a3-171">Le nom du champ est différent selon le scénario, mais la description du champ indique le message suivant : « Remarque : ce numéro sera utilisé uniquement si personnalisé est sélectionné dans le menu déroulant. »</span><span class="sxs-lookup"><span data-stu-id="4b9a3-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="4b9a3-172">En règle générale, les valeurs <STRONG>élevé</STRONG>, <STRONG>moyen</STRONG>et <STRONG>faible</STRONG> modifient les taux de conversation par modalité en fonction du modèle utilisateur qui est un bilan de tous les scénarios.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="4b9a3-173">S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence d’utilisation prévue, nous vous recommandons d’utiliser une fréquence de conversation <STRONG>personnalisée</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4b9a3-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="4b9a3-174">Scénarios vocaux</span><span class="sxs-lookup"><span data-stu-id="4b9a3-174">Voice Scenarios</span></span>

<span data-ttu-id="4b9a3-175">L’onglet **scénarios vocaux** de l’outil de configuration de chargement de Lync Server 2013 est présenté dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="4b9a3-176">Utilisez l’onglet **scénarios vocaux** pour configurer tous les scénarios liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="4b9a3-177">![Onglet scénarios vocaux.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Onglet scénarios vocaux.")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="4b9a3-178">Dans **VoIP**, cliquez sur le bouton **avancé** , puis spécifiez des valeurs pour les champs **PhoneAreaCode** et **LocationProfile** (plan de numérotation).</span><span class="sxs-lookup"><span data-stu-id="4b9a3-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="4b9a3-179">Vous devez également spécifier une valeur pour le **niveau de charge**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="4b9a3-180">Si le niveau de \*\*\*\* charge des **passerelles VoIP et RTC/PSTN** est activé, un fichier de configuration de réseau téléphonique commuté (PSTN) vers des communications unifiées (UC) est toujours généré qui simule des appels externes.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="4b9a3-181">Dans **passerelle UC/PSTN**, spécifiez une valeur pour niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="4b9a3-182">Si vous sélectionnez un niveau de charge différent de **désactivé**, vous devez indiquer une valeur pour le **Code de zone RTC** en cliquant sur le bouton **Ajouter** sous serveur de médiation et RTC.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="4b9a3-183">Vérifiez que vous disposez d’un itinéraire configuré pour ce code de zone.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b9a3-184">Vous pouvez utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell pour vérifier la configuration des itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="4b9a3-185">Dans le **surveillant de conférences**, spécifiez une valeur pour le niveau de charge.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="4b9a3-186">Le choix d’un niveau de charge (différent de **désactivé**) permettra d’activer le champ **numéro de téléphone** .</span><span class="sxs-lookup"><span data-stu-id="4b9a3-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="4b9a3-187">Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="4b9a3-188">Cliquez sur le bouton **avancé** , puis spécifiez une valeur pour le champ **LocationProfile** .</span><span class="sxs-lookup"><span data-stu-id="4b9a3-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="4b9a3-189">Dans **service de parc d’appels**, spécifiez la valeur appropriée pour le **niveau de charge**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="4b9a3-190">Sur le **serveur de médiation et sur PSTN**, pour chaque serveur de médiation que vous souhaitez utiliser, vous devez disposer d’un simulateur PSTN distinct.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="4b9a3-191">Une fois que vous avez déterminé le client que vous allez utiliser comme simulateur, vous devez configurer votre serveur de médiation pour router les appels vers cet ordinateur sur le port de simulateur PSTN que vous avez configuré.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="4b9a3-192">Cliquez sur **Ajouter** pour configurer la valeur du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b9a3-193">Dans chacun des scénarios, un bouton <STRONG>avancé</STRONG> est placé en regard.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="4b9a3-194">Ces boutons autorisent l’accès à des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), et activez la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="4b9a3-195">Pour chaque scénario sous l’onglet <STRONG>scénarios vocaux</STRONG> , si la valeur de <STRONG>niveau de charge</STRONG> est <STRONG>personnalisée</STRONG>, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4b9a3-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="4b9a3-196">Le nom du champ est différent selon le scénario, mais la description du champ indique le message suivant : « Remarque : ce numéro sera utilisé uniquement si personnalisé est sélectionné dans le menu déroulant. »</span><span class="sxs-lookup"><span data-stu-id="4b9a3-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="4b9a3-197">Arrivez</span><span class="sxs-lookup"><span data-stu-id="4b9a3-197">Reach</span></span>

<span data-ttu-id="4b9a3-198">La fonction joindre est une nouvelle interface de Lync Server 2013 qui prend en charge les scénarios de conférence via le serveur UCWA (Unified Communications Web API) installé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="4b9a3-199">L’onglet **joindre** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="4b9a3-200">Utilisez l’onglet **joindre** pour configurer tous les scénarios liés à la portée.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="4b9a3-201">![Onglet joindre](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Onglet joindre")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="4b9a3-202">Cliquez sur le bouton **avancé** en regard de **paramètres d’atteinte générale**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="4b9a3-203">Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool de réalisateurs ou le VIP du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="4b9a3-204">Dans **partage d’application**, **collaboration de données**et **messagerie instantanée**, sélectionnez la valeur appropriée pour le **niveau de charge**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b9a3-205">Dans chacun des scénarios, un bouton <STRONG>avancé</STRONG> est placé en regard.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="4b9a3-206">Ces boutons autorisent l’accès à des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), et activez la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="4b9a3-207">Pour chacun des scénarios d’atteinte, si le <STRONG>niveau de charge</STRONG> est <STRONG>personnalisé</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="4b9a3-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="4b9a3-208">Utilisez l’onglet **mobilité** pour configurer tous les scénarios liés à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="4b9a3-209">![Onglet mobilité.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Onglet mobilité.")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="4b9a3-210">Cliquez sur le bouton **avancé** en regard de **mobilité (UCWA)**.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="4b9a3-211">Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool de réalisateurs ou le VIP du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="4b9a3-212">Sur le **son de présence et\\de messagerie instantanée P2P**, sélectionnez la valeur appropriée pour **niveau de charge** pour activer la simulation de scénarios de mobilité.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b9a3-213">Dans chacun des scénarios, un bouton <STRONG>avancé</STRONG> est placé en regard.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="4b9a3-214">Ces boutons autorisent l’accès à des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), et activez la personnalisation.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="4b9a3-215">Pour chacun des scénarios d’atteinte, si le <STRONG>niveau de charge</STRONG> est <STRONG>personnalisé</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="4b9a3-216">Résumé</span><span class="sxs-lookup"><span data-stu-id="4b9a3-216">Summary</span></span>

<span data-ttu-id="4b9a3-217">L’onglet **Résumé** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="4b9a3-218">![Onglet Résumé.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Onglet Résumé.")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="4b9a3-219">L’onglet **Résumé** indique quels utilisateurs utiliser pour chacun des scénarios.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="4b9a3-220">Il est possible de configurer manuellement la plage des numéros d’utilisateur en activant la case à cocher Activer la génération de plages d' **utilisateurs personnalisés** , puis en double-cliquant sur le scénario dans la table dont vous souhaitez **personnaliser la plage d’utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="4b9a3-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="4b9a3-221">Regardez (RunClient. bat) ajoutez un délai de connexion au démarrage, afin d’inclure les retards dans les fichiers de commandes générés pour correspondre au taux de connexion.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="4b9a3-222">Cela peut s’avérer utile pour éviter une surcharge du serveur lors de la connexion d’un grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="4b9a3-223">Cliquez sur **générer des fichiers**, puis sélectionnez le dossier dans lequel vous voulez générer la configuration.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="4b9a3-224">Une boîte de dialogue similaire à la figure suivante s’affichera lors de la création de vos fichiers.</span><span class="sxs-lookup"><span data-stu-id="4b9a3-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="4b9a3-225">![Accusé de réception de la création de fichiers.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Accusé de réception de la création de fichiers.")</span><span class="sxs-lookup"><span data-stu-id="4b9a3-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b9a3-226">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b9a3-226">See Also</span></span>


[<span data-ttu-id="4b9a3-227">Créer des utilisateurs et des contacts</span><span class="sxs-lookup"><span data-stu-id="4b9a3-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
