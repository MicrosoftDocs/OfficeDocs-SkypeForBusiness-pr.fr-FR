---
title: Créer des utilisateurs et des contacts
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f90e6cbb1afb9c4c2dd2b43e1448ca635899531b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="f3386-102">Créer des utilisateurs et des contacts</span><span class="sxs-lookup"><span data-stu-id="f3386-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3386-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f3386-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f3386-104">Vous devez utiliser l’outil de mise en service utilisateur Lync Server 2013 (UserProvisioningTool.exe) pour créer des utilisateurs et des contacts en vue de préparer le test de charge des performances et de la contrainte.</span><span class="sxs-lookup"><span data-stu-id="f3386-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="f3386-105">Voici une liste des termes et des définitions que vous pouvez trouver utiles lors de la lecture de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f3386-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="f3386-106">Unité d’organisation : l’unité d’organisation des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3386-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="f3386-107">Fédérés/interpools : utilisateurs qui seront autorisés à communiquer avec des utilisateurs à partir d’autres services de messagerie instantanée, tels que MSN Network of Internet Services, AOL® et Yahoo \! ®.</span><span class="sxs-lookup"><span data-stu-id="f3386-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="f3386-108">Listes de distribution : objets des services de domaine Active Directory qui contiennent une liste des utilisateurs des services de domaine Active Directory, utilisés pour lancer des communications avec des groupes de personnes.</span><span class="sxs-lookup"><span data-stu-id="f3386-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="f3386-109">Service d’informations d’emplacement : le service Lync Server 2013 qui, lorsqu’il est activé et configuré par téléphone, permet la récupération de l’emplacement physique des services Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="f3386-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="f3386-110">Numéros de téléphone des États-Unis : numéros de téléphone affectés aux utilisateurs, en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants et la recherche de numéros inversées (RNL).</span><span class="sxs-lookup"><span data-stu-id="f3386-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="f3386-111">Créer des utilisateurs et des contacts à l’aide de UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="f3386-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="f3386-112">Vous devez utiliser l’outil de mise en service d’utilisateur Lync Server pour créer des utilisateurs et des contacts pour la simulation de charge.</span><span class="sxs-lookup"><span data-stu-id="f3386-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="f3386-113">L’outil de mise en service des utilisateurs Lync Server est installé avec le package d’outils de performances et de stress de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3386-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="f3386-114">Assurez-vous que le programme d’installation du package (CapacityPlanningTool.msi) a été exécuté sur le serveur frontal ou le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3386-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="f3386-115">Démarrez l’outil de mise en service des utilisateurs Lync Server en exécutant le fichier UserProvisioningTool.exe (situé dans le dossier% InstalledDirectory% LyncStressAndPerfTool \\ LyncStress) sur le serveur frontal ou sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3386-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f3386-116">Vous devez être connecté en tant que membre du groupe de sécurité administrateurs du domaine afin d’exécuter UserProvisioningTool.exe.</span><span class="sxs-lookup"><span data-stu-id="f3386-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="f3386-117">Il est nécessaire d’exécuter à partir de ce contexte car UserProvisioningTool.exe créerez et configurerez les nouveaux utilisateurs des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3386-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f3386-118">Lorsque vous créez un nombre important d’utilisateurs (10 000 ou plus), exécutez UserProvisioningTool.exe à partir d’un ordinateur haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="f3386-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="f3386-119">Notez que le contrôleur de domaine subira également une charge élevée pendant que les utilisateurs sont en cours de création.</span><span class="sxs-lookup"><span data-stu-id="f3386-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="f3386-120">Lorsque l’outil de mise en service de l’utilisateur Lync Server s’ouvre, cliquez sur **configuration** , puis sélectionnez **charger la configuration**.</span><span class="sxs-lookup"><span data-stu-id="f3386-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="f3386-121">Pour commencer à configurer des utilisateurs et des contacts, chargez le fichier par défaut inclus dans le package, SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="f3386-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="f3386-122">Cette opération préremplira les champs avec des exemples de données que vous devrez réviser pour votre système.</span><span class="sxs-lookup"><span data-stu-id="f3386-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="f3386-123">Si vous disposez d’un fichier XML préconfiguré qui contient déjà des paramètres personnalisés, chargez ce fichier à la place.</span><span class="sxs-lookup"><span data-stu-id="f3386-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="f3386-124">Renseignez les champs de l’outil de mise en service d’utilisateur Lync Server, comme décrit dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="f3386-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="f3386-125">![Onglet création d’utilisateur.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Onglet création d’utilisateur.")</span><span class="sxs-lookup"><span data-stu-id="f3386-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="f3386-126">Pour configurer les options de serveur, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f3386-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="f3386-127">Dans nom de domaine **complet du pool frontal**, tapez le nom de domaine complet (FQDN) du serveur Standard Edition ou du pool frontal où vous voulez héberger les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f3386-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="f3386-128">Dans **préfixe du nom d’utilisateur**, tapez un préfixe que vous souhaitez utiliser pour créer des noms d’utilisateurs à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="f3386-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="f3386-129">Dans **mot de passe**, spécifiez un mot de passe qui sera appliqué à tous les comptes d’utilisateur test.</span><span class="sxs-lookup"><span data-stu-id="f3386-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="f3386-130">Dans **domaine SIP**, tapez le nom de domaine à utiliser pour les URI SIP (Uniform Resource Identifiers) des utilisateurs test.</span><span class="sxs-lookup"><span data-stu-id="f3386-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="f3386-131">Dans **domaine de compte**, tapez le nom de domaine de votre domaine des services de domaine Active Directory actuel, sous lequel vous souhaitez créer les utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="f3386-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="f3386-132">Dans **unité d’organisation**, tapez le nom de l’unité d’organisation des services de domaine Active Directory dans laquelle vous souhaitez créer les objets utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="f3386-133">Si l’unité d’organisation n’existe pas, elle sera créée.</span><span class="sxs-lookup"><span data-stu-id="f3386-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="f3386-134">Dans **Code de zone de téléphone**, tapez le code de zone à trois chiffres qui sera utilisé pour les comptes d’utilisateur test.</span><span class="sxs-lookup"><span data-stu-id="f3386-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="f3386-135">Assurez-vous que le code de la zone téléphonique n’entre pas en conflit avec les autres codes de zone des utilisateurs dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3386-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="f3386-136">Activez la case à cocher **voix activée** si vous souhaitez activer les utilisateurs de test pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="f3386-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="f3386-137">Dans **nombre d’utilisateurs**, spécifiez le nombre total d’utilisateurs test que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="f3386-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="f3386-138">Dans **index de début**, spécifiez le numéro de départ qui sera utilisé comme suffixe du préfixe du nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="f3386-139">Bouton créer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f3386-139">Create Users Button</span></span>

<span data-ttu-id="f3386-140">Lorsque vous cliquez sur le bouton créer des utilisateurs, il valide tous les paramètres d’entrée.</span><span class="sxs-lookup"><span data-stu-id="f3386-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="f3386-141">S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.</span><span class="sxs-lookup"><span data-stu-id="f3386-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="f3386-142">Si toutes les valeurs d’entrée sont correctes, il commence à créer des utilisateurs dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3386-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="f3386-143">Une barre de progression s’affiche au bas de ce formulaire.</span><span class="sxs-lookup"><span data-stu-id="f3386-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="f3386-144">Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.</span><span class="sxs-lookup"><span data-stu-id="f3386-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="f3386-145">La création de l’utilisateur est un processus lent.</span><span class="sxs-lookup"><span data-stu-id="f3386-145">User Creation is a slow process.</span></span> <span data-ttu-id="f3386-146">Cette opération peut prendre plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="f3386-146">It can take several minutes.</span></span> <span data-ttu-id="f3386-147">Si le nombre d’utilisateurs est très important, le processus peut prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="f3386-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="f3386-148">Si les utilisateurs existent déjà, ils sont mis à jour avec les modifications.</span><span class="sxs-lookup"><span data-stu-id="f3386-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="f3386-149">Vous pouvez vérifier que les utilisateurs ont été créés en ouvrant une session en tant que l’un des utilisateurs de la plage.</span><span class="sxs-lookup"><span data-stu-id="f3386-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="f3386-150">Utilisez le préfixe d’utilisateur, le numéro d’utilisateur et le @sipDomain comme nom d’utilisateur (par exemple, LyncUser10@contoso.net), ainsi que le mot de passe spécifié.</span><span class="sxs-lookup"><span data-stu-id="f3386-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="f3386-151">Bouton supprimer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f3386-151">Delete Users Button</span></span>

<span data-ttu-id="f3386-152">Lorsque vous cliquez sur le bouton supprimer des utilisateurs, il valide tous les paramètres d’entrée.</span><span class="sxs-lookup"><span data-stu-id="f3386-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="f3386-153">S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.</span><span class="sxs-lookup"><span data-stu-id="f3386-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="f3386-154">Si toutes les valeurs d’entrée sont correctes, il commencera à désactiver et à supprimer les utilisateurs dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f3386-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="f3386-155">Une barre de progression s’affiche au bas de ce formulaire.</span><span class="sxs-lookup"><span data-stu-id="f3386-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="f3386-156">Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.</span><span class="sxs-lookup"><span data-stu-id="f3386-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="f3386-157">Seuls les numéros de téléphone au format américain sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f3386-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="f3386-158">Les numéros de téléphone sont toujours attribués aux utilisateurs et tous les utilisateurs créés par UserProvisioningTool.exe sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="f3386-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f3386-159">Tous les scénarios qui utilisent le numéro de téléphone, comme les appels de standard automatique de conférence ou RTC-PSTN, utilisent ce numéro de téléphone pour acheminer correctement les appels.</span><span class="sxs-lookup"><span data-stu-id="f3386-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="f3386-160">Pour cette raison, chaque utilisateur doit disposer d’un numéro de téléphone unique.</span><span class="sxs-lookup"><span data-stu-id="f3386-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="f3386-161">Si vous devez créer des utilisateurs à deux reprises, la commande échoue, sauf si vous utilisez un indicatif régional différent ou si les utilisateurs précédents ont été désactivés à l’aide de la cmdlet <STRONG>Disable-Csuser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f3386-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="f3386-162">Avant de créer des contacts, vous devez d’abord effectuer une réplication utilisateur, effectuée à partir de l’onglet utilisateurs. Si vous venez de créer vos utilisateurs, vous devez patienter jusqu’à ce que la réplication Lync Server se termine et renseigne les comptes d’utilisateur dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f3386-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="f3386-163">Si les utilisateurs n’ont pas terminé la réplication, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f3386-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="f3386-164">Vous saurez quand les utilisateurs ont terminé la réplication si le service frontal Lync Server 2013 a démarré ou en exécutant correctement la cmdlet <STRONG>Get-Csuser</STRONG> sur le dernier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="f3386-165">Onglet Création de contacts</span><span class="sxs-lookup"><span data-stu-id="f3386-165">Contacts Creation Tab</span></span>

<span data-ttu-id="f3386-166">L’onglet Création de contacts vous permet de spécifier les détails des contacts des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f3386-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="f3386-167">![Onglet Création de contacts.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Onglet Création de contacts.")</span><span class="sxs-lookup"><span data-stu-id="f3386-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="f3386-168">Pour configurer les contacts des utilisateurs, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f3386-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="f3386-169">Dans moyenne des contacts par utilisateur, spécifiez le nombre moyen de contacts à remplir dans les listes de contacts pour chacun des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f3386-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="f3386-170">Activez la case à cocher fixe si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="f3386-171">Si vous souhaitez modifier le nombre de contacts créés pour les utilisateurs, désactivez la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="f3386-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="f3386-172">Dans moyenne des groupes de contacts par utilisateur, spécifiez le nombre de groupes de contacts par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="f3386-173">Ce nombre doit être inférieur à la moyenne des contacts par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="f3386-174">Dans le pourcentage de contacts fédérés/de pool croisé, spécifiez un nombre compris entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="f3386-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="f3386-175">Ce pourcentage de contacts est créé avec les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="f3386-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="f3386-176">Dans le préfixe d’utilisateur fédéré/de pool croisé, spécifiez le nom d’utilisateur des utilisateurs fédérés qui seront ajoutés aux listes de contacts des utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="f3386-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="f3386-177">Dans domaine SIP d’utilisateur fédéré/de pool croisé, spécifiez le nom de domaine SIP des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="f3386-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3386-178">Aucun utilisateur ne doit être connecté lors de la création de contacts.</span><span class="sxs-lookup"><span data-stu-id="f3386-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="f3386-179">Dans l’onglet création d’utilisateur, vérifiez que les paramètres sont corrects.</span><span class="sxs-lookup"><span data-stu-id="f3386-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="f3386-180">La plage d’utilisateurs pour laquelle les contacts seront créés est obtenue à partir de l’onglet Création de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="f3386-181">Cliquez sur créer des contacts pour commencer la création du contact.</span><span class="sxs-lookup"><span data-stu-id="f3386-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="f3386-182">Ce processus peut prendre plusieurs minutes.</span><span class="sxs-lookup"><span data-stu-id="f3386-182">This process can take several minutes.</span></span> <span data-ttu-id="f3386-183">Une fois l’opération terminée, une boîte de dialogue s’affiche avec le message « l’opération s’est déroulée correctement ».</span><span class="sxs-lookup"><span data-stu-id="f3386-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="f3386-184">Vous pouvez valider les contacts qui ont été créés en ouvrant une session en tant qu’utilisateur créé à partir de l’onglet création d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3386-185">Une fois les contacts créés, cet outil redémarrera tous les serveurs frontaux dans le pool cible.</span><span class="sxs-lookup"><span data-stu-id="f3386-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="f3386-186">Le démarrage des serveurs frontaux peut prendre plus de temps (jusqu’à 2 heures), selon le nombre de contacts créés par cette opération.</span><span class="sxs-lookup"><span data-stu-id="f3386-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="f3386-187">Liste de distribution</span><span class="sxs-lookup"><span data-stu-id="f3386-187">Distribution List</span></span>

<span data-ttu-id="f3386-188">L’une des fonctionnalités de l’outil stress and performance de Lync Server 2013 consiste à simuler la fonctionnalité d’extension de liste de distribution (DL) dans Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f3386-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="f3386-189">Si vous ne souhaitez pas activer le développement de la LD dans UserProvisioningTool, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="f3386-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="f3386-190">![Onglet Création de liste de distribution.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Onglet Création de liste de distribution.")</span><span class="sxs-lookup"><span data-stu-id="f3386-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="f3386-191">L’onglet Liste de distribution vous permet de créer des listes de distribution que l’outil stress and performance utilisera pour la fonctionnalité d’extension de liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="f3386-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="f3386-192">Avant de créer des listes de distribution, Lync Server 2013 doit déjà être installé.</span><span class="sxs-lookup"><span data-stu-id="f3386-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="f3386-193">Vous devez avoir exécuté Lync Server 2013 ForestPrep.</span><span class="sxs-lookup"><span data-stu-id="f3386-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="f3386-194">Dans le cas contraire, les attributs DL n’existent pas dans le schéma des services de domaine Active Directory et l’outil ne pourra pas créer de listes de distribution.</span><span class="sxs-lookup"><span data-stu-id="f3386-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="f3386-195">Pour configurer les listes de distribution, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f3386-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="f3386-196">Dans nombre de listes de distribution, spécifiez le nombre total de listes de distribution que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="f3386-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="f3386-197">(Nous vous recommandons de commencer avec deux fois le nombre d’utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="f3386-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="f3386-198">Ils sont numérotés de 0 à n-1.</span><span class="sxs-lookup"><span data-stu-id="f3386-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="f3386-199">Dans préfixe de liste de distribution, spécifiez le préfixe que devra posséder les listes de distribution.</span><span class="sxs-lookup"><span data-stu-id="f3386-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="f3386-200">Par exemple, si vous spécifiez 100 DL et un préfixe testDL, les listes de distribution seront nommées testDL0, testDL1, et ainsi de suite, via testDL99.</span><span class="sxs-lookup"><span data-stu-id="f3386-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="f3386-201">Dans membres minimum d’une liste dist., spécifiez le nombre minimal d’utilisateurs à ajouter dans chaque liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="f3386-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="f3386-202">Dans nombre maximal de membres dans une liste dist., spécifiez le nombre maximal d’utilisateurs à ajouter dans chaque liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="f3386-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="f3386-203">Bouton créer des listes de distribution</span><span class="sxs-lookup"><span data-stu-id="f3386-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="f3386-204">Lorsque vous cliquez sur le bouton créer des listes de distribution, l’outil interroge les services de domaine Active Directory pour déterminer si les listes de distribution correspondant au préfixe et aux numéros existent déjà.</span><span class="sxs-lookup"><span data-stu-id="f3386-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="f3386-205">L’outil crée uniquement ceux qui n’existent pas encore.</span><span class="sxs-lookup"><span data-stu-id="f3386-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="f3386-206">Lorsque vous ajoutez des membres à ces listes de distribution nouvellement créées, les utilisateurs sont sélectionnés dans la plage spécifiée dans l’onglet création d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f3386-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="f3386-207">Onglet Configuration du service informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="f3386-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="f3386-208">L’une des fonctionnalités de l’outil stress and performance de Lync Server 2013 est de générer des fichiers de configuration factices pour le service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="f3386-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="f3386-209">En règle générale, le service informations d’emplacement n’a pas d’impact significatif sur les performances des serveurs.</span><span class="sxs-lookup"><span data-stu-id="f3386-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="f3386-210">![Onglet Configuration du service informations d’emplacement.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Onglet Configuration du service informations d’emplacement.")</span><span class="sxs-lookup"><span data-stu-id="f3386-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="f3386-211">Si vous choisissez de tester cette fonctionnalité, vous pouvez renseigner les valeurs mentionnées dans le formulaire, puis cliquer sur le bouton générer des fichiers de configuration LIS.</span><span class="sxs-lookup"><span data-stu-id="f3386-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="f3386-212">Il génère des fichiers CSV appelés LIS \_Subnet.csv, lis \_Switches.csv, lis \_Ports.csv et lis \_WAP.csv.</span><span class="sxs-lookup"><span data-stu-id="f3386-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="f3386-213">Vous pouvez ensuite importer ces fichiers CSV dans la base de données LIS à l’aide de la cmdlet **Set-CsLisSubnet** , de l’applet de commande Set **-CsLisSwitch** , de l’applet de commande **Set-CsLisPort** et de l’applet de commande **Set-CsWirelessAccessPoint** .</span><span class="sxs-lookup"><span data-stu-id="f3386-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

