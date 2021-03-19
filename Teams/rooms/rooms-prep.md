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
description: Découvrez comment préparer votre infrastructure pour le déploiement de salles Microsoft Teams afin de tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 181599e6b5181f50548621e4895b400f442646a6
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884568"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="c415c-103">Préparer votre environnement</span><span class="sxs-lookup"><span data-stu-id="c415c-103">Prepare your environment</span></span>

<span data-ttu-id="c415c-104">Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous pouvez utiliser toutes les fonctionnalités des salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c415c-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="c415c-105">Préparez un compte d’appareil pour chaque console de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c415c-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="c415c-106">Pour [plus d’informations, voir](rooms-deploy.md) Déployer les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c415c-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="c415c-107">Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil. </span><span class="sxs-lookup"><span data-stu-id="c415c-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="c415c-108">Il doit être en mesure de recevoir une adresse IP à l’aide de DHCP.</span><span class="sxs-lookup"><span data-stu-id="c415c-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="c415c-109">(Les salles Microsoft Teams ne peuvent pas être configurées avec une adresse IP statique au démarrage de la première unité, mais par la suite, une adresse IP statique pour l’appareil peut être configurée sur l’appareil ou sur le commutateur ou le routeur en amont.)</span><span class="sxs-lookup"><span data-stu-id="c415c-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="c415c-110">Ces ports doivent être ouverts (en plus des ports normaux pour les médias) :</span><span class="sxs-lookup"><span data-stu-id="c415c-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="c415c-111">HTTPS : 443</span><span class="sxs-lookup"><span data-stu-id="c415c-111">HTTPS: 443</span></span>
   - <span data-ttu-id="c415c-112">HTTP : 80</span><span class="sxs-lookup"><span data-stu-id="c415c-112">HTTP: 80</span></span>

   <span data-ttu-id="c415c-113">Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.</span><span class="sxs-lookup"><span data-stu-id="c415c-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="c415c-114">Les salles Microsoft Teams ne prend pas en charge l’authentification du proxy, car elle peut interférer avec les opérations régulières de la salle.</span><span class="sxs-lookup"><span data-stu-id="c415c-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="c415c-115">Avant de passer en production, assurez-vous que les salles Microsoft Teams ont été exemptées de l’authentification du proxy.</span><span class="sxs-lookup"><span data-stu-id="c415c-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="c415c-116">Pour améliorer votre expérience, Microsoft collecte des données.</span><span class="sxs-lookup"><span data-stu-id="c415c-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="c415c-117">Pour autoriser Microsoft à collecter des données, autorisez les sites ci-après :</span><span class="sxs-lookup"><span data-stu-id="c415c-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="c415c-118">Point de terminaison du client de télémétrie : https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="c415c-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="c415c-119">Point de terminaison des paramètres de télémétrie : https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="c415c-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="c415c-120">Création et test d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="c415c-120">Create and test a device account</span></span>

<span data-ttu-id="c415c-121">Un  *compte d’appareil*  est un compte que le client Salles Microsoft Teams utilise pour accéder aux fonctionnalités d’Exchange, telles que le calendrier, et activer Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c415c-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="c415c-122">Pour [plus d’informations, voir](rooms-deploy.md) Déployer les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c415c-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="c415c-123">Vérification de la disponibilité du réseau</span><span class="sxs-lookup"><span data-stu-id="c415c-123">Check network availability</span></span>

<span data-ttu-id="c415c-124">Pour fonctionner correctement, l’appareil Salles Microsoft Teams doit avoir accès à un réseau câblé qui répond aux conditions requises :</span><span class="sxs-lookup"><span data-stu-id="c415c-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="c415c-125">Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c415c-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="c415c-126">Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP.</span><span class="sxs-lookup"><span data-stu-id="c415c-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="c415c-127">Les salles Microsoft Teams ne peuvent pas être configurées avec une adresse IP statique au démarrage de la première unité.</span><span class="sxs-lookup"><span data-stu-id="c415c-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="c415c-128">Accès aux ports HTTP 80 et 443.</span><span class="sxs-lookup"><span data-stu-id="c415c-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="c415c-129">Ports TCP et UDP configurés comme décrit dans la configuration requise pour les ports et protocoles pour les serveurs pour les implémentations Skype Entreprise Server sur site, ou les URL et plages d’adresses [IP Microsoft 365 et Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour les implémentations en ligne de Microsoft Teams ou de Skype Entreprise. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)</span><span class="sxs-lookup"><span data-stu-id="c415c-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c415c-130">Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. </span><span class="sxs-lookup"><span data-stu-id="c415c-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="c415c-131">Les mises à jour logicielles des salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="c415c-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="c415c-132">Consultez [les conditions préalables pour que Microsoft Store](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) pour Entreprises et Éducation vérifie que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="c415c-132">See [Prerequisites for Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="c415c-133">Certificats</span><span class="sxs-lookup"><span data-stu-id="c415c-133">Certificates</span></span>

<span data-ttu-id="c415c-134">Votre appareil Salles Microsoft Teams utilise des certificats pour les services web Exchange, Microsoft Teams ou Skype Entreprise, l’utilisation du réseau et l’authentification.</span><span class="sxs-lookup"><span data-stu-id="c415c-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="c415c-135">Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats.</span><span class="sxs-lookup"><span data-stu-id="c415c-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="c415c-136">En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA).</span><span class="sxs-lookup"><span data-stu-id="c415c-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="c415c-137">L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c415c-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="c415c-138">Vous installerez les certificats comme vous le feriez pour tout autre client Windows. </span><span class="sxs-lookup"><span data-stu-id="c415c-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c415c-139">Des certificats peuvent être nécessaires pour que les salles Microsoft Teams utilisent Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c415c-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="c415c-140">Proxy</span><span class="sxs-lookup"><span data-stu-id="c415c-140">Proxy</span></span>

<span data-ttu-id="c415c-141">Les salles Microsoft Teams sont conçues pour hériter des paramètres proxy du système d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="c415c-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="c415c-142">Accédez au système d’exploitation Windows de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="c415c-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="c415c-143">Dans l’interface utilisateur de Salles Microsoft Teams, cliquez sur l’icône d’engrenage Paramètres dans laquelle vous serez invité à consulter le mot de passe administrateur local sur l’appareil (le mot de passe par défaut **est sfb).**</span><span class="sxs-lookup"><span data-stu-id="c415c-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="c415c-144">Appuyez sur **Paramètres,** puis sur le bouton Aller  à **Windows,** puis sur le  bouton Se connectez-vous à l’administrateur, puis cliquez sur le bouton Administrateur (si l’ordinateur est joint au domaine, sélectionnez Autre **utilisateur,** puis utilisez .\admin comme nom d’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="c415c-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="c415c-145">Dans la **zone Rechercher dans Windows,** tapez le type en bas à gauche dans regedit (appuyez longuement sur l’écran ou cliquez avec le bouton droit et sélectionnez **Exécuter en tant qu’administrateur).**</span><span class="sxs-lookup"><span data-stu-id="c415c-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="c415c-146">Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c415c-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="c415c-147">Cliquez sur Fichier, puis **sélectionnez Charger la ruche.**</span><span class="sxs-lookup"><span data-stu-id="c415c-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="c415c-148">Accédez au **dossier C:\Users\Skype,** tapez le nom de fichier dans la zone NOMFAUX.dat, puis appuyez sur le bouton ouvrir.</span><span class="sxs-lookup"><span data-stu-id="c415c-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="c415c-149">Vous êtes invité à nommer la clé de votre ruche nouvellement chargée. dans Skype (vous devez maintenant voir les paramètres du Registre de l’utilisateur Skype).</span><span class="sxs-lookup"><span data-stu-id="c415c-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="c415c-150">Ouvrez la clé Skype et naviguez jusquHKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings vous assurer que les paramètres sont entrés :</span><span class="sxs-lookup"><span data-stu-id="c415c-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="c415c-151">Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.</span><span class="sxs-lookup"><span data-stu-id="c415c-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="c415c-152">Si le client utilise un fichier PAC, la configuration doit ressembler à l’exemple ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c415c-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="c415c-153">Une fois que vous avez terminé vos modifications, mettez en surbrillance la clé Utilisateur Skype (dossier racine pour Skype) et choisissez de décharger Hive du menu de fichier Registre (vous serez invité à confirmer - sélectionnez **Oui**).</span><span class="sxs-lookup"><span data-stu-id="c415c-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="c415c-154">Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.</span><span class="sxs-lookup"><span data-stu-id="c415c-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="c415c-155">De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**.</span><span class="sxs-lookup"><span data-stu-id="c415c-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="c415c-156">Si toutes les étapes précédentes ont réussi, l’appareil Salles Microsoft Teams se connecte avec succès.</span><span class="sxs-lookup"><span data-stu-id="c415c-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="c415c-157">Pour plus [d’informations](https://docs.microsoft.com/microsoftteams/rooms/security#network-security) sur les FQDN, ports et plages d’adresses IP requis pour les salles Microsoft Teams, consultez l’article sur la sécurité réseau.</span><span class="sxs-lookup"><span data-stu-id="c415c-157">See the [Network Security](https://docs.microsoft.com/microsoftteams/rooms/security#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="c415c-158">Création de packages de mise en service</span><span class="sxs-lookup"><span data-stu-id="c415c-158">Create provisioning packages</span></span>

<span data-ttu-id="c415c-159">Vous utiliserez des packages d’approvisionnement pour vous authentifier Exchange Server, Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="c415c-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="c415c-160">Gestion du groupe d’administrateurs</span><span class="sxs-lookup"><span data-stu-id="c415c-160">Admin group management</span></span>

<span data-ttu-id="c415c-161">Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine.</span><span class="sxs-lookup"><span data-stu-id="c415c-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="c415c-162">Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.</span><span class="sxs-lookup"><span data-stu-id="c415c-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c415c-163">Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres.</span><span class="sxs-lookup"><span data-stu-id="c415c-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="c415c-164">La solution consiste à se connecter avec le compte d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="c415c-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="c415c-165">Comptes locaux</span><span class="sxs-lookup"><span data-stu-id="c415c-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="c415c-166">Compte d’utilisateur local salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c415c-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="c415c-167">Le compte d’appareil n’utilise généralement pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c415c-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="c415c-168">Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire.</span><span class="sxs-lookup"><span data-stu-id="c415c-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="c415c-169">Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c415c-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="c415c-170">"Admin" - Compte d’administrateur local</span><span class="sxs-lookup"><span data-stu-id="c415c-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="c415c-171">Le mot de passe par défaut des salles Microsoft Teams est définie sur « sfb ».</span><span class="sxs-lookup"><span data-stu-id="c415c-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="c415c-172">Le mot de passe peut être modifié localement en vous rendant dans les Paramètres Windows, dans Windows ou dans le fichier AutoUnattend.xml (utilisez le Gestionnaire d’images système Windows d’ADK pour apporter la modification au fichier \> xml).</span><span class="sxs-lookup"><span data-stu-id="c415c-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c415c-173">N’oubliez pas de modifier le mot de passe des salles Microsoft Teams dès que possible.</span><span class="sxs-lookup"><span data-stu-id="c415c-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="c415c-174">Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="c415c-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="c415c-175">Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="c415c-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="c415c-176">Compte d’ordinateur</span><span class="sxs-lookup"><span data-stu-id="c415c-176">Machine Account</span></span>

<span data-ttu-id="c415c-177">Tout comme sur n’importe quel appareil Windows, vous pouvez renommer le nom de l’ordinateur en cliquant avec le bouton droit dans **Paramètres** À propos \>  \> **de Renommer le PC.**</span><span class="sxs-lookup"><span data-stu-id="c415c-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="c415c-178">Si vous voulez renommer l’ordinateur après l’avoir joint à un domaine, utilisez **Renommer** l’ordinateur, une commande PowerShell, suivie du nouveau nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c415c-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c415c-179">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c415c-179">Related topics</span></span>

[<span data-ttu-id="c415c-180">Planifier des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c415c-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="c415c-181">Spécifications des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c415c-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="c415c-182">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c415c-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="c415c-183">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c415c-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="c415c-184">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c415c-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="c415c-185">Conditions préalables au Microsoft Store pour Entreprises et Éducation</span><span class="sxs-lookup"><span data-stu-id="c415c-185">Prerequisites for Microsoft Store for Business and Education</span></span>](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
