---
title: Préparer votre environnement
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Découvrez comment préparer votre infrastructure pour le déploiement d Salles Microsoft Teams de manière à tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117422"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="f5cdd-103">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="f5cdd-103">Prepare your environment</span></span>

<span data-ttu-id="f5cdd-104">Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous pouvez utiliser toutes les fonctionnalités de Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="f5cdd-105">Préparez un compte d’appareil pour Salles Microsoft Teams console mobile.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="f5cdd-106">Pour [plus d’Salles Microsoft Teams](rooms-deploy.md) consultez La liste des déploiements.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="f5cdd-107">Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil. </span><span class="sxs-lookup"><span data-stu-id="f5cdd-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="f5cdd-108">Il doit être en mesure de recevoir une adresse IP à l’aide de DHCP.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="f5cdd-109">(Salles Microsoft Teams ne peut pas être configuré avec une adresse IP statique au démarrage de la première unité, mais par la suite, une adresse IP statique pour l’appareil peut être configurée sur l’appareil ou sur le commutateur ou le routeur en amont.)</span><span class="sxs-lookup"><span data-stu-id="f5cdd-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="f5cdd-110">Ces ports doivent être ouverts (en plus des ports normaux pour les médias) :</span><span class="sxs-lookup"><span data-stu-id="f5cdd-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="f5cdd-111">HTTPS : 443</span><span class="sxs-lookup"><span data-stu-id="f5cdd-111">HTTPS: 443</span></span>
   - <span data-ttu-id="f5cdd-112">HTTP : 80</span><span class="sxs-lookup"><span data-stu-id="f5cdd-112">HTTP: 80</span></span>

   <span data-ttu-id="f5cdd-113">Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="f5cdd-114">Salles Microsoft Teams ne prend pas en charge l’authentification du proxy, car elle peut interférer avec les opérations régulières de la salle.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="f5cdd-115">Avant de passer en production, assurez-Salles Microsoft Teams avez été exemptés de l’authentification du proxy.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="f5cdd-116">Pour améliorer votre expérience, Microsoft collecte des données.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="f5cdd-117">Pour autoriser Microsoft à collecter des données, autorisez les sites ci-après :</span><span class="sxs-lookup"><span data-stu-id="f5cdd-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="f5cdd-118">Point de terminaison du client de télémétrie : https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="f5cdd-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="f5cdd-119">Point de terminaison des paramètres de télémétrie : https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="f5cdd-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="f5cdd-120">Création et test d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="f5cdd-120">Create and test a device account</span></span>

<span data-ttu-id="f5cdd-121">Un *compte d’appareil* est un compte que le client Salles Microsoft Teams utilise pour accéder aux fonctionnalités de Exchange, telles que le calendrier, et pour activer Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="f5cdd-122">Pour [plus d’Salles Microsoft Teams](rooms-deploy.md) consultez La liste des déploiements.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="f5cdd-123">Vérification de la disponibilité du réseau</span><span class="sxs-lookup"><span data-stu-id="f5cdd-123">Check network availability</span></span>

<span data-ttu-id="f5cdd-124">Pour fonctionner correctement, l’Salles Microsoft Teams doit avoir accès à un réseau câblé qui répond aux exigences ci-après :</span><span class="sxs-lookup"><span data-stu-id="f5cdd-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="f5cdd-125">Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="f5cdd-126">Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="f5cdd-127">Salles Microsoft Teams ne peut pas être configuré avec une adresse IP statique au démarrage de la première unité.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="f5cdd-128">Accès aux ports HTTP 80 et 443.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="f5cdd-129">Ports TCP et UDP configurés comme décrit dans la configuration requise pour les ports et protocoles pour les serveurs pour les implémentations Skype Entreprise Server en local, ou les URL et plages d’adresses [IP Microsoft 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) et Office 365 pour les implémentations en ligne Microsoft Teams ou Skype Entreprise. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)</span><span class="sxs-lookup"><span data-stu-id="f5cdd-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5cdd-130">Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. </span><span class="sxs-lookup"><span data-stu-id="f5cdd-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="f5cdd-131">Les mises à jour logicielles Salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="f5cdd-132">Consultez [les conditions préalables Microsoft Store pour Entreprises et](/microsoft-store/prerequisites-microsoft-store-for-business) Éducation pour vérifier que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="f5cdd-133">Certificats</span><span class="sxs-lookup"><span data-stu-id="f5cdd-133">Certificates</span></span>

<span data-ttu-id="f5cdd-134">Votre Salles Microsoft Teams utilise des certificats pour les services Exchange web, l’Microsoft Teams ou la Skype Entreprise, l’utilisation du réseau et l’authentification.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="f5cdd-135">Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="f5cdd-136">En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="f5cdd-137">L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="f5cdd-138">Vous installerez les certificats comme vous le feriez pour tout autre client Windows. </span><span class="sxs-lookup"><span data-stu-id="f5cdd-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f5cdd-139">Des certificats peuvent être nécessaires pour être utilisés Salles Microsoft Teams et Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="f5cdd-140">Proxy</span><span class="sxs-lookup"><span data-stu-id="f5cdd-140">Proxy</span></span>

<span data-ttu-id="f5cdd-141">Salles Microsoft Teams est conçu pour hériter des paramètres proxy du système d’Windows système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="f5cdd-142">Accédez au système d’exploitation Windows de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="f5cdd-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="f5cdd-143">Dans l’interface utilisateur Salles Microsoft Teams, cliquez sur l’icône d’engrenage Paramètres dans laquelle vous êtes invité à consulter le mot de passe administrateur local sur l’appareil (le mot de passe par défaut est **sfb).**</span><span class="sxs-lookup"><span data-stu-id="f5cdd-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="f5cdd-144">Appuyez sur **Paramètres** puis sur le bouton Aller à **Windows,** puis  sur le bouton Se connectez-vous à l’administrateur, puis cliquez sur le bouton Administrateur (si l’ordinateur est joint au domaine, sélectionnez Autre  **utilisateur,** puis utilisez .\admin comme nom d’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="f5cdd-145">Dans la **zone Rechercher Windows** tapez en bas à gauche dans regedit (appuyez longuement sur l’écran ou cliquez avec le bouton droit et sélectionnez Exécuter en tant **qu’administrateur).**</span><span class="sxs-lookup"><span data-stu-id="f5cdd-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="f5cdd-146">Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="f5cdd-147">Cliquez sur Fichier, puis **sélectionnez Charger la ruche.**</span><span class="sxs-lookup"><span data-stu-id="f5cdd-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="f5cdd-148">Accédez au **dossier C:\Users\Skype,** tapez le nom de fichier dans la zone NOMFAUX.dat, puis appuyez sur le bouton ouvrir</span><span class="sxs-lookup"><span data-stu-id="f5cdd-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="f5cdd-149">Vous êtes invité à nommer la clé de votre ruche nouvellement chargée. tapez dans Skype (vous devez à présent voir les paramètres du Registre de l Skype un utilisateur).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="f5cdd-150">Ouvrez la Skype clé d’accès et HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings vérifier que ces paramètres sont entrés :</span><span class="sxs-lookup"><span data-stu-id="f5cdd-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="f5cdd-151">Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="f5cdd-152">Si le client utilise un fichier PAC, la configuration doit ressembler à l’exemple ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="f5cdd-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="f5cdd-153">Une fois que vous avez terminé vos modifications, mettez en surbrillance la clé Utilisateur Skype (dossier racine pour Skype) et choisissez de décharger Hive du menu de fichier Registre (vous serez invité à confirmer - sélectionnez **Oui**).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="f5cdd-154">Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="f5cdd-155">De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="f5cdd-156">Si toutes les étapes précédentes ont réussi, l Salles Microsoft Teams appareil se connecte correctement.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="f5cdd-157">Pour plus [d’informations](./security.md#network-security) sur les FQDN, ports et plages d’adresses IP requis pour les Salles Microsoft Teams, voir l’article sur la sécurité réseau.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="f5cdd-158">Création de packages de mise en service</span><span class="sxs-lookup"><span data-stu-id="f5cdd-158">Create provisioning packages</span></span>

<span data-ttu-id="f5cdd-159">Vous utiliserez des packages d’approvisionnement pour vous authentifier à des Exchange Server, Microsoft 365, ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="f5cdd-160">Gestion du groupe d’administrateurs</span><span class="sxs-lookup"><span data-stu-id="f5cdd-160">Admin group management</span></span>

<span data-ttu-id="f5cdd-161">Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="f5cdd-162">Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f5cdd-163">Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="f5cdd-164">La solution consiste à se connecter avec le compte d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="f5cdd-165">Comptes locaux</span><span class="sxs-lookup"><span data-stu-id="f5cdd-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="f5cdd-166">Salles Microsoft Teams Compte d’utilisateur local</span><span class="sxs-lookup"><span data-stu-id="f5cdd-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="f5cdd-167">Le compte d’appareil n’utilise généralement pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="f5cdd-168">Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="f5cdd-169">Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="f5cdd-170">"Admin" - Compte d’administrateur local</span><span class="sxs-lookup"><span data-stu-id="f5cdd-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="f5cdd-171">Salles Microsoft Teams mot de passe par défaut est définie sur « sfb ».</span><span class="sxs-lookup"><span data-stu-id="f5cdd-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="f5cdd-172">Le mot de passe peut être modifié localement en vous rendant dans Windows Paramètres Go to Windows ou dans le fichier AutoUnattend.xml (utilisez le gestionnaire d’images système Windows de ADK pour apporter la modification au fichier \> xml).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f5cdd-173">N’oubliez pas de modifier Salles Microsoft Teams mot de passe dès que possible.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="f5cdd-174">Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="f5cdd-175">Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="f5cdd-176">Compte d’ordinateur</span><span class="sxs-lookup"><span data-stu-id="f5cdd-176">Machine Account</span></span>

<span data-ttu-id="f5cdd-177">À l’Windows n’importe quel appareil, vous pouvez renommer le nom de l’ordinateur en cliquant avec le bouton droit **Paramètres** À propos \>  \> **de Renommer le PC.**</span><span class="sxs-lookup"><span data-stu-id="f5cdd-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="f5cdd-178">Si vous voulez renommer l’ordinateur après l’avoir joint à un domaine, utilisez **Renommer** l’ordinateur, une commande PowerShell, suivie du nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f5cdd-179">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f5cdd-179">Related topics</span></span>

[<span data-ttu-id="f5cdd-180">Planifier Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5cdd-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="f5cdd-181">Spécifications des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5cdd-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="f5cdd-182">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5cdd-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="f5cdd-183">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5cdd-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="f5cdd-184">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5cdd-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="f5cdd-185">Conditions préalables pour les Microsoft Store pour Entreprises et l’éducation</span><span class="sxs-lookup"><span data-stu-id="f5cdd-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)