---
title: Créer des utilisateurs et des contacts
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f09ac6fd667b77b47e27ec9fb9caac44b9a13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="a9773-102">Créer des utilisateurs et des contacts</span><span class="sxs-lookup"><span data-stu-id="a9773-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9773-103">_**Dernière modification de la rubrique:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a9773-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a9773-104">Vous devez utiliser l’outil de mise en service des utilisateurs de Lync Server 2013 (UserProvisioningTool. exe) pour créer des utilisateurs et des contacts en préparation au test de charge de stress et de performance.</span><span class="sxs-lookup"><span data-stu-id="a9773-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="a9773-105">Vous trouverez ci-dessous une liste de termes et de définitions qui peuvent vous intéresser lorsque vous lisez ce sujet.</span><span class="sxs-lookup"><span data-stu-id="a9773-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="a9773-106">Unité d’organisation-l’unité d’organisation Active Directory Domain Services (UO).</span><span class="sxs-lookup"><span data-stu-id="a9773-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="a9773-107">Regroupement fédéré/croisé: les utilisateurs qui pourront communiquer avec des utilisateurs à partir d’autres services de messagerie instantanée, tels que le réseau MSN de services Internet, le® AOL et Yahoo\!®.</span><span class="sxs-lookup"><span data-stu-id="a9773-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="a9773-108">Listes de distribution: objets dans les services de domaine Active Directory (AD FS) qui contiennent une liste des utilisateurs des services de domaine Active Directory (AD FS) utilisés pour le lancement des communications avec des groupes de personnes.</span><span class="sxs-lookup"><span data-stu-id="a9773-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="a9773-109">Service des informations de géolocalisation: le service Lync Server 2013 qui, lorsqu’il est activé ou configuré par téléphone, autorise la récupération de l’emplacement physique pour les services Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="a9773-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="a9773-110">Numéros de téléphone américains: les numéros de téléphone affectés aux utilisateurs, en plus de l’URI SIP utilisé pour le routage des appels entrants et sortants et la recherche de numéros inversés (RNL).</span><span class="sxs-lookup"><span data-stu-id="a9773-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="a9773-111">Créer des utilisateurs et des contacts à l’aide de UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="a9773-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="a9773-112">Vous devez utiliser l’outil de mise en service de l’utilisateur de Lync Server pour créer des utilisateurs et des contacts pour la simulation de chargement.</span><span class="sxs-lookup"><span data-stu-id="a9773-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="a9773-113">L’outil de mise en service de l’utilisateur Lync Server est installé avec le package d’outils de stress et de performance de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9773-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="a9773-114">Assurez-vous que le programme d’installation de package (CapacityPlanningTool. msi) a été exécuté sur le serveur frontal ou sur le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="a9773-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="a9773-115">Démarrez l’outil de mise en service de l’utilisateur Lync Server en exécutant le fichier UserProvisioningTool. exe (qui se trouve\\à% InstalledDirectory% LyncStressAndPerfTool LyncStress) sur le serveur frontal ou sur le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="a9773-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9773-116">Vous devez être connecté en tant que membre du groupe de sécurité administrateurs de domaine pour pouvoir exécuter UserProvisioningTool. exe.</span><span class="sxs-lookup"><span data-stu-id="a9773-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="a9773-117">Il est nécessaire de procéder à une exécution à partir du contexte, car UserProvisioningTool. exe crée et configure de nouveaux utilisateurs de services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9773-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a9773-118">Lorsque vous créez un nombre d’utilisateurs important (10 000 ou plus), exécutez UserProvisioningTool. exe à partir d’un ordinateur haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="a9773-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="a9773-119">Notez que le contrôleur de domaine fonctionne également en charge lors de la création des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="a9773-120">Lorsque l’outil de mise en service de l’utilisateur Lync Server s’ouvre, cliquez sur **configuration** , puis sélectionnez **charger la configuration**.</span><span class="sxs-lookup"><span data-stu-id="a9773-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="a9773-121">Pour commencer à configurer les utilisateurs et les contacts, chargez le fichier par défaut inclus dans le package, SampleData. Xml.</span><span class="sxs-lookup"><span data-stu-id="a9773-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="a9773-122">Cette opération préremplira les champs avec des exemples de données que vous devrez modifier pour votre système.</span><span class="sxs-lookup"><span data-stu-id="a9773-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="a9773-123">Si vous avez un fichier XML préconfiguré qui contient déjà des paramètres personnalisés, chargez ce fichier à la place.</span><span class="sxs-lookup"><span data-stu-id="a9773-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="a9773-124">Renseignez les champs de l’outil de mise en service de l’utilisateur Lync Server, comme décrit dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="a9773-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="a9773-125">![Onglet création d’utilisateur.] (images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Onglet création d’utilisateur.")</span><span class="sxs-lookup"><span data-stu-id="a9773-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="a9773-126">Pour configurer les options du serveur, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9773-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="a9773-127">Dans nom de domaine complet (FQDN) du **pool frontal**, tapez le nom de domaine complet (FQDN) du serveur Standard Edition ou du pool frontal sur lequel vous souhaitez héberger les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="a9773-128">Dans **nom d’utilisateur**, entrez le préfixe que vous souhaitez utiliser pour créer des noms d’utilisateur à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="a9773-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="a9773-129">Dans **mot de passe**, spécifiez un mot de passe qui sera appliqué à tous les comptes d’utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="a9773-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="a9773-130">Dans **domaine SIP**, tapez le nom de domaine à utiliser pour les URI SIP des utilisateurs test (Uniform Resource Identifiers).</span><span class="sxs-lookup"><span data-stu-id="a9773-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="a9773-131">Dans **domaine de compte**, tapez le nom de domaine de votre domaine de services de domaine Active Directory actuel, sous lequel vous voulez créer les utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="a9773-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="a9773-132">Dans **unité d’organisation**, tapez le nom de l’unité d’organisation Active Directory Domain Services dans laquelle vous voulez créer les objets utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="a9773-133">S’il n’existe pas, il sera créé.</span><span class="sxs-lookup"><span data-stu-id="a9773-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="a9773-134">Dans **Code de la zone téléphonique**, tapez le code de zone à trois chiffres qui sera utilisé pour les comptes d’utilisateurs test.</span><span class="sxs-lookup"><span data-stu-id="a9773-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="a9773-135">Assurez-vous que le code de zone téléphonique n’entre pas en conflit avec les codes de zone des autres utilisateurs dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9773-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="a9773-136">Activez la case à cocher **voix activée** si vous souhaitez activer l’option voix entreprise pour les utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="a9773-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="a9773-137">Dans **nombre d’utilisateurs**, spécifiez le nombre total d’utilisateurs de test que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="a9773-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="a9773-138">Dans **index de début**, spécifiez le numéro de départ qui sera utilisé comme suffixe du préfixe du nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="a9773-139">Bouton créer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a9773-139">Create Users Button</span></span>

<span data-ttu-id="a9773-140">Lorsque vous cliquez sur le bouton créer des utilisateurs, tous les paramètres d’entrée sont validés.</span><span class="sxs-lookup"><span data-stu-id="a9773-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="a9773-141">S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a9773-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="a9773-142">Si toutes les valeurs d’entrée sont correctes, la création des utilisateurs dans les services de domaine Active Directory va commencer.</span><span class="sxs-lookup"><span data-stu-id="a9773-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="a9773-143">Une barre de progression apparaît au bas du formulaire.</span><span class="sxs-lookup"><span data-stu-id="a9773-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="a9773-144">Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.</span><span class="sxs-lookup"><span data-stu-id="a9773-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="a9773-145">Le processus de création d’utilisateur est lent.</span><span class="sxs-lookup"><span data-stu-id="a9773-145">User Creation is a slow process.</span></span> <span data-ttu-id="a9773-146">Quelques minutes peuvent être nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a9773-146">It can take several minutes.</span></span> <span data-ttu-id="a9773-147">Si le nombre d’utilisateurs est très grand, le processus peut même prendre quelques heures.</span><span class="sxs-lookup"><span data-stu-id="a9773-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="a9773-148">Si les utilisateurs existent déjà, ils sont mis à jour avec les modifications apportées.</span><span class="sxs-lookup"><span data-stu-id="a9773-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="a9773-149">Vous pouvez vérifier que les utilisateurs ont été créés en se connectant comme l’un des utilisateurs de la plage.</span><span class="sxs-lookup"><span data-stu-id="a9773-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="a9773-150">Utilisez le préfixe d’utilisateur, le numéro d’utilisateur et le @sipDomain comme nom d’utilisateur (par exemple, LyncUser10@contoso.net), ainsi que le mot de passe spécifié.</span><span class="sxs-lookup"><span data-stu-id="a9773-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="a9773-151">Bouton supprimer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a9773-151">Delete Users Button</span></span>

<span data-ttu-id="a9773-152">Lorsque vous cliquez sur le bouton supprimer des utilisateurs, tous les paramètres d’entrée sont validés.</span><span class="sxs-lookup"><span data-stu-id="a9773-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="a9773-153">S’il existe des erreurs de validation, il vous invite à corriger ces valeurs d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a9773-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="a9773-154">Si toutes les valeurs d’entrée sont correctes, elles commenceront à désactiver et à supprimer des utilisateurs dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="a9773-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="a9773-155">Une barre de progression apparaît au bas du formulaire.</span><span class="sxs-lookup"><span data-stu-id="a9773-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="a9773-156">Nous vous recommandons de ne pas fermer l’application lorsque la barre de progression est active.</span><span class="sxs-lookup"><span data-stu-id="a9773-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="a9773-157">Seuls les numéros de téléphone au format U.S. sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a9773-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="a9773-158">Les numéros de téléphone sont toujours attribués aux utilisateurs, et tous les utilisateurs créés par UserProvisioningTool. exe sont activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a9773-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="a9773-159">Tout scénario utilisant le numéro de téléphone, comme le standard automatique des conférences ou les appels RTC, utilisez ce numéro de téléphone pour acheminer correctement les appels.</span><span class="sxs-lookup"><span data-stu-id="a9773-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="a9773-160">C’est pourquoi chaque utilisateur doit avoir un numéro de téléphone unique.</span><span class="sxs-lookup"><span data-stu-id="a9773-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="a9773-161">Si vous devez créer des utilisateurs à deux reprises, la commande échouera, sauf si vous utilisez un indicatif de zone différent ou si les utilisateurs précédents ont été désactivés à l’aide de l’applet de commande <STRONG>Disable-Csuser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a9773-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="a9773-162">Avant de créer des contacts, vous devez commencer par procéder à la réplication des utilisateurs, à partir de l’onglet utilisateurs. Si vous venez de créer vos utilisateurs, vous devez attendre la fin de la réplication de Lync Server et remplir les comptes d’utilisateurs dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a9773-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="a9773-163">Si les utilisateurs n’ont pas terminé la réplication, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a9773-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="a9773-164">Vous savez alors que les utilisateurs ont fini de procéder à la réplication si le service frontal de Lync Server 2013 a démarré ou en exécutant correctement l’applet de passe <STRONG>Get-Csuser</STRONG> sur le dernier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="a9773-165">Onglet Création de contacts</span><span class="sxs-lookup"><span data-stu-id="a9773-165">Contacts Creation Tab</span></span>

<span data-ttu-id="a9773-166">L’onglet Création de contacts vous permet de spécifier les détails des contacts des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="a9773-167">![Onglet Création de contacts.] (images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Onglet Création de contacts.")</span><span class="sxs-lookup"><span data-stu-id="a9773-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="a9773-168">Pour configurer les contacts des utilisateurs, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9773-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="a9773-169">Dans les contacts moyens par utilisateur, spécifiez le nombre moyen de contacts à renseigner dans les listes de contacts pour chacun des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="a9773-170">Activez la case à cocher fixe si vous souhaitez créer un nombre égal de contacts pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="a9773-171">Si vous voulez modifier le nombre de contacts créés pour les utilisateurs, décochez la case.</span><span class="sxs-lookup"><span data-stu-id="a9773-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="a9773-172">Dans les groupes de contacts moyens par utilisateur, spécifiez le nombre de groupes de contacts par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="a9773-173">Ce numéro doit être inférieur à la moyenne des contacts par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="a9773-174">Dans la section pourcentage du nombre de contacts du pool fédéré/du groupe croisé, spécifiez un nombre compris entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="a9773-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="a9773-175">Ce pourcentage de contacts sera créé avec les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="a9773-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="a9773-176">Dans le cas d’un préfixe d’utilisateur pour les pools fédéré et Cross, spécifiez le nom d’utilisateur des utilisateurs fédérés qui seront ajoutés aux listes de contacts des utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="a9773-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="a9773-177">Dans domaine SIP pour les utilisateurs fédérés/ThreadPool, spécifiez le nom de domaine SIP des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="a9773-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9773-178">Aucun utilisateur ne doit être connecté lors de la création de contacts.</span><span class="sxs-lookup"><span data-stu-id="a9773-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="a9773-179">Dans l’onglet création d’utilisateur, vérifiez que les paramètres sont corrects.</span><span class="sxs-lookup"><span data-stu-id="a9773-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="a9773-180">Le nombre d’utilisateurs pour lesquels les contacts seront créés est obtenu à partir de l’onglet création d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="a9773-181">Cliquez sur créer des contacts pour commencer la création du contact.</span><span class="sxs-lookup"><span data-stu-id="a9773-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="a9773-182">Ce processus peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="a9773-182">This process can take several minutes.</span></span> <span data-ttu-id="a9773-183">Une fois qu’elle est terminée, une boîte de dialogue s’affiche avec le message «opération terminée correctement».</span><span class="sxs-lookup"><span data-stu-id="a9773-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="a9773-184">Vous pouvez valider les contacts créés en vous connectant en tant qu’utilisateur créé à partir de l’onglet création d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9773-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9773-185">Une fois les contacts créés, vous redémarrez tous les serveurs frontaux dans la liste cible.</span><span class="sxs-lookup"><span data-stu-id="a9773-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="a9773-186">Le début de la période (jusqu’à 2 heures) est susceptible de durer plus longtemps, selon le nombre de contacts créés par cette opération.</span><span class="sxs-lookup"><span data-stu-id="a9773-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="a9773-187">Liste de distribution</span><span class="sxs-lookup"><span data-stu-id="a9773-187">Distribution List</span></span>

<span data-ttu-id="a9773-188">L’une des fonctionnalités de l’outil de stress et de performance de Lync Server 2013 consiste à simuler la fonctionnalité d’extension de liste de distribution dans Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a9773-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="a9773-189">Si vous n’êtes pas en mesure d’activer l’extension DL dans UserProvisioningTool, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="a9773-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="a9773-190">![Onglet Création de liste de distribution.] (images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Onglet Création de liste de distribution.")</span><span class="sxs-lookup"><span data-stu-id="a9773-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="a9773-191">L’onglet Liste de distribution vous permet de créer des listes de distribution que l’outil de stress et de performance utilisera pour la fonctionnalité d’extension de liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="a9773-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="a9773-192">Avant de créer des listes de distribution, Lync Server 2013 doit déjà être installé.</span><span class="sxs-lookup"><span data-stu-id="a9773-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="a9773-193">Vous devez avoir exécuté Lync Server 2013 ForestPrep.</span><span class="sxs-lookup"><span data-stu-id="a9773-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="a9773-194">Dans le cas contraire, les attributs DL n’existent pas dans le schéma des services de domaine Active Directory et l’outil ne peut pas créer de DL.</span><span class="sxs-lookup"><span data-stu-id="a9773-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="a9773-195">Pour configurer des listes de distribution, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a9773-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="a9773-196">Dans nombre de listes de distribution, spécifiez le nombre total de DL que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="a9773-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="a9773-197">(Nous vous recommandons d’utiliser deux fois le nombre d’utilisateurs).</span><span class="sxs-lookup"><span data-stu-id="a9773-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="a9773-198">Ils sont numérotés de 0 à n-1.</span><span class="sxs-lookup"><span data-stu-id="a9773-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="a9773-199">Dans préfixe de la liste de distribution, spécifiez le préfixe de la liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="a9773-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="a9773-200">Par exemple, si vous spécifiez des listes de distribution 100 et un préfixe de testDL, les listes de distribution seront nommées testDL0, testDL1, etc., via testDL99.</span><span class="sxs-lookup"><span data-stu-id="a9773-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="a9773-201">Dans membres minimum d’une liste de dist., spécifiez le nombre minimum d’utilisateurs à ajouter dans chaque liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="a9773-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="a9773-202">Dans nombre maximal de membres d’une liste de dist., spécifiez le nombre maximal d’utilisateurs à ajouter dans chaque liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="a9773-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="a9773-203">Bouton créer des listes de distribution</span><span class="sxs-lookup"><span data-stu-id="a9773-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="a9773-204">Lorsque vous cliquez sur le bouton créer des listes de distribution, l’outil interroge les services de domaine Active Directory pour voir si les listes de distribution correspondant au préfixe et aux numéros existent déjà.</span><span class="sxs-lookup"><span data-stu-id="a9773-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="a9773-205">L’outil crée uniquement ceux qui n’existent pas déjà.</span><span class="sxs-lookup"><span data-stu-id="a9773-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="a9773-206">Lors de l’ajout de membres à ces listes de distribution nouvellement créées, les utilisateurs sont sélectionnés dans la plage spécifiée dans l’onglet création d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="a9773-207">Onglet Configuration du service informations de géolocalisation</span><span class="sxs-lookup"><span data-stu-id="a9773-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="a9773-208">L’une des fonctionnalités de l’outil de stress et de performance de Lync Server 2013 consiste à générer des fichiers de configuration factices pour le service d’information d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="a9773-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="a9773-209">En règle générale, le service des informations d’emplacement n’a pas d’impact important sur les performances sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="a9773-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="a9773-210">![Onglet Configuration du service informations] de géolocalisation. (images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Onglet Configuration du service informations") de géolocalisation.</span><span class="sxs-lookup"><span data-stu-id="a9773-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="a9773-211">Si vous choisissez de tester cette fonctionnalité, vous pouvez renseigner les valeurs mentionnées dans le formulaire, puis cliquer sur le bouton générer les fichiers de configuration de LIS.</span><span class="sxs-lookup"><span data-stu-id="a9773-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="a9773-212">Il génère des fichiers CSV nommés LIS\_subnet. csv, lis\_switchs. csv,\_lis ports. csv et lis\_WAP. csv.</span><span class="sxs-lookup"><span data-stu-id="a9773-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="a9773-213">Vous pouvez ensuite importer ces fichiers CSV dans la base de données LIS à l’aide de l’applet de cmdlet **Set-CsLisSubnet** , de l’applet de applet Set- **CsLisSwitch** , de l’applet de passe **Set-CsLisPort** et de l’applet **de passe Set-CsWirelessAccessPoint** , respectivement.</span><span class="sxs-lookup"><span data-stu-id="a9773-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

