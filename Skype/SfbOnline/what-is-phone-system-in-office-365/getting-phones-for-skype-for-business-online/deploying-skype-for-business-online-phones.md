---
title: Déploiement de téléphones Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Apprenez les étapes de déploiement pour obtenir le microprogramme correct, le mettre à jour si nécessaire, affecter les licences, et configurer les paramètres des téléphones Skype Entreprise Online
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780061"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="fda5d-103">Déploiement de téléphones Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="fda5d-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="fda5d-104">Ce guide de déploiement vous aidera à déployer des téléphones IP Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="fda5d-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="fda5d-p101">Dans tous les types d'entreprises, disposer d'un numéro de téléphone permet aux utilisateurs de passer et de recevoir des appels vocaux, ce qui est une condition importante pour faire des affaires. Les utilisateurs disposant de numéros de téléphone pourront passer des appels vocaux vers tous les appareils Skype Entreprise y compris les téléphones IP, les PC et les appareils mobiles. Vous pouvez en apprendre plus sur les téléphones IP Skype Entreprise en lisant [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="fda5d-p101">In all types of businesses, having a phone number allows users to make and get voice calls and it is an important requirement to do business. Users that have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by seeing, [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="fda5d-108">Étapes de déploiement des téléphones IP</span><span class="sxs-lookup"><span data-stu-id="fda5d-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="fda5d-109">Étape 1 : télécharger les guides de l'administrateur et les manuels de téléphone du fabricant</span><span class="sxs-lookup"><span data-stu-id="fda5d-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="fda5d-110">Avant de commencer, il est pertinent de télécharger les guides d'administration et les manuels de téléphone du fabricant.</span><span class="sxs-lookup"><span data-stu-id="fda5d-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="fda5d-111">Pour les téléphones Polycom, voir le [Guide de déploiement Polycom]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="fda5d-111">For Polycom phones, see the http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="fda5d-112">Pour les téléphones Yealink, voir [Solution de téléphones HD SIP Skype Entreprise Yealink](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="fda5d-112">For Yealink phones, see [Yealink Skype for Business® HD IP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="fda5d-113">Dans le cas de téléphones AudioCodes, consultez le guide [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="fda5d-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="fda5d-114">Étape 2 : assurez-vous que vous achetez ou que vous faites migrer un téléphone IP et un microprogramme pris en charge par Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="fda5d-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="fda5d-p102">Un téléphone IP et un microprogramme pris en charge par Skype Entreprise Online sont également compatibles avec Skype Entreprise Server, mais l'inverse n'est pas toujours vrai. Pour vous assurer que vous achetez ou que vous approvisionnez un téléphone et un microprogramme pris en charge, voir [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="fda5d-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) guide.</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="fda5d-117">Étape 3 : vérification du fait que le microprogramme adéquat est installé et mettre à jour le microprogramme si nécessaire</span><span class="sxs-lookup"><span data-stu-id="fda5d-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="fda5d-p103">Vérifiez la version du microprogramme sur vos téléphones. Pour :</span><span class="sxs-lookup"><span data-stu-id="fda5d-p103">To check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="fda5d-120">**les téléphones Polycom VVX,**, accédez à **Settings (Paramètres)** > **Status (Statut)** > **Platform (Plate-forme)** > **Application** > **Main (Principal)**.</span><span class="sxs-lookup"><span data-stu-id="fda5d-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="fda5d-121">**les téléphones Yealink**, accédez à **Status (Statut)** sur l'écran principal.</span><span class="sxs-lookup"><span data-stu-id="fda5d-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="fda5d-122">**les téléphones AudioCodes**, accédez à **Menu** > **Device Status (Statut de l'appareil)** > **Firmware version (Version du microprogramme)** dans l'écran d'accueil.</span><span class="sxs-lookup"><span data-stu-id="fda5d-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fda5d-p104">Pour l'accès à distance aux détails des téléphones, reportez-vous aux guides d'administration du fabricant. Voir les liens ci-dessus pour les modes d'emploi et les manuels des téléphones.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p104">For remote access to phone details refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="fda5d-125">**les téléphones Lync Phone Edition (LPE)**, accédez à **Menu** > **System Information (Informations système)** dans l'écran d'accueil.</span><span class="sxs-lookup"><span data-stu-id="fda5d-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="fda5d-126">Étape 4 : remarques sur la mise à jour des appareils</span><span class="sxs-lookup"><span data-stu-id="fda5d-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="fda5d-p105">Le microprogramme Polycom antérieur à la version 5.5.1.X disposait d'un mécanisme de verrouillage de l'appareil spécifique au fabricant qui est remplacé par une implémentation "Phone-Lock" de Skype Entreprise. La mise à jour d'un téléphone depuis la version 5.4.X.X qui était sécurisée par "Device-Lock" vers la version 5.5.1.X avec "Phone-Lock" n'héritera pas du code confidentiel du "Device-Lock", ce qui peut laisser le téléphone non sécurisé. Les utilisateurs qui ont activé la fonction "Device-Lock" doivent activer le paramètre suivant du Profil d'appareil Polycom pour donner le contrôle aux utilisateurs du moment de la mise à niveau (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="fda5d-p105">Polycom firmware prior to 5.5.1.X had a manufacturer specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock". Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock", which can leave the phone unsecured. For users who have activated "Device-Lock", you need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="fda5d-p106">Les mises à jour de microprogramme sont gérées par le service Skype Entreprise. Chaque microprogramme de téléphone certifié Skype Entreprise est chargé sur le serveur de mise à jour Skype Entreprise, et la mise à jour de l'appareil est activée par défaut sur tous les téléphones. En fonction de la durée d'inactivité sur le téléphone et des intervalles d'interrogation, les téléphones téléchargeront et installeront automatiquement les versions certifiées les plus récentes. Vous pouvez désactiver les paramètres de mise à jour des appareils en utilisant le cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) et en définissant le paramètre _EnableDeviceUpdate_ à `false`.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Déploiement de téléphones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="fda5d-p107">Lorsqu'un nouveau microprogramme sera disponible et prêt à être téléchargé et installé, le téléphone en informera l'utilisateur. Les téléphones Polycom en informeront l'utilisateur et lui fourniront une option pour **Mettre à jour**, ou **Reporter**.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update**, or **Postpone**.</span></span>
  
![Déploiement de téléphones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="fda5d-138">Dans le cas d'un téléphone Polycom, vous pouvez mettre à jour le microprogramme en sélectionnant **SwUpdate (Mise à jour logicielle)**.</span><span class="sxs-lookup"><span data-stu-id="fda5d-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Déploiement de téléphones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="fda5d-p108">Vous pouvez également gérer les mises à jour du microprogramme à l'aide d'un système de provisionnement partenaire. Pour plus d'informations sur la gestion de système de provisionnement partenaire, notamment la personnalisation de téléphone avancée, consultez les guide d'administration du fabricant.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fda5d-142">Veillez à disposer d'une seule autorité de mise à jour pour l'appareil (mise à jour intrabande ou serveur de provisionnement tiers) pour éviter toute boucle de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="fda5d-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="fda5d-143">Étape 5 : paramètres de téléphone de configuration et d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="fda5d-143">Step 5 - Configure and infrastructure phone settings</span></span>

<span data-ttu-id="fda5d-p109">Vous pouvez configurer les options et stratégies téléphoniques les plus utilisées à l'aide d'applets de commande Windows PowerShell de gestion intrabande pour Skype Entreprise. Consultez le lien [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) pour plus de détails sur ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="fda5d-146">Pour la planification de l’infrastructure réseau, voir [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="fda5d-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/) andDeploy, Migrate, and Roll Out.</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="fda5d-147">Étape 6 : préparation de la connexion des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fda5d-147">Step 6 - Preparing for users to sign-in</span></span>

<span data-ttu-id="fda5d-p110">Pour permettre aux utilisateurs de se connecter à un téléphone Skype Entreprise Online et de passer des appels, vous devez vous assurer que les licences adéquates ont été affectées aux utilisateurs. Au minimum, vous devez leur affecter une licence Système téléphonique et un Plan d'appels. Pour plus d'informations, vous pouvez voir [Octroi de licences de modules complémentaires Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) et[Affecter des licences Skype Entreprise et Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="fda5d-p110">To enable users to successfully sign-on to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum you will need to assign a Skype for Business Cloud PBX license and a PSTN Calling plan. For additional information you can see [Skype for Business add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) .</span></span>
  
<span data-ttu-id="fda5d-151">Vous pouvez trouver plus d’informations sur les Plans d'appels en lisant [Quels sont les Plans d’appels dans Office 365 ?](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="fda5d-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="fda5d-152">Les **options de connexion** disponibles pour les utilisateurs Online sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fda5d-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="fda5d-153">Les utilisateurs de téléphones **Polycom VVX 5XX/6XX** verront :</span><span class="sxs-lookup"><span data-stu-id="fda5d-153">For those users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Déploiement de téléphones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="fda5d-155">Les utilisateurs de téléphones **Yealink T48G/T46G** verront :</span><span class="sxs-lookup"><span data-stu-id="fda5d-155">For those users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Ouverture de session des téléphones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="fda5d-157">Pour des détails sur les options de connexion prises en charge par le fabricant, voir [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="fda5d-157">For details on sign-in options supported by manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="fda5d-p111">**ID d'utilisateur** À l'aide de leur clavier téléphonique ou de leur clavier visuel (le cas échéant), les utilisateurs peuvent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. : *amosm@contoso.com*  pour leur nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Déploiement de téléphones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="fda5d-161">L'authentification par code confidentiel n'est pas prise en charge par Skype Entreprise Online avec les téléphones LPE et PIP (Partner IP Phone).</span><span class="sxs-lookup"><span data-stu-id="fda5d-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="fda5d-p112">**Utilisation d'un PC** Quand le logiciel Better Together over Ethernet (BToE) est installé et activé sur le PC d'un utilisateur, les utilisateurs peuvent se connecter à leur téléphone en utilisant la fenêtre d'authentification de leur application Skype Entreprise Windows. Voir [Étape 7 (facultative) : si vous avez le couplage d'appareil et Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log into their phone using the authentication window on their Windows Skype for Business App. See[Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fda5d-p113">Les utilisateurs doivent se servir du nom d'utilisateur et du mot de passe de leur organisation pour se connecter à leur téléphone. Par exemple, ils doivent utiliser le format UPN (par ex. :  *amosm@contoso.com*  pour leur nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Déploiement de téléphones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="fda5d-p114">**Utilisation d'une connexion par web** : il s'agit d'une nouvelle méthode pour les utilisateurs en ligne pour s'authentifier en utilisant un navigateur web standard. Les utilisateurs recevront un ensemble d'instructions à suivre lorsqu'ils utilisent un navigateur pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p114">**Using a** Web Sign-in: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign-in.</span></span>
    
  - <span data-ttu-id="fda5d-169">Les utilisateurs de téléphones **Polycom VVX 5XX/6XX** verront :</span><span class="sxs-lookup"><span data-stu-id="fda5d-169">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Déploiement de téléphones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="fda5d-171">Les utilisateurs de téléphones **Yealink T48G/T46G** verront :</span><span class="sxs-lookup"><span data-stu-id="fda5d-171">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Ouverture de session des téléphones Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="fda5d-p115">Le code généré expirera dans 15 minutes. Quand il aura expiré, l'utilisateur devra cliquer sur **Réessayer** ou sur **OK** pour générer un nouveau code, en fonction du téléphone.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code depending on the phone.</span></span>
    
  - <span data-ttu-id="fda5d-175">Les utilisateurs de téléphones **Polycom VVX 5XX/6XX** verront :</span><span class="sxs-lookup"><span data-stu-id="fda5d-175">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Code confidentiel expiré.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="fda5d-177">Les utilisateurs de téléphones **Yealink T48G/T46G** verront :</span><span class="sxs-lookup"><span data-stu-id="fda5d-177">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Ouverture de session des téléphones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="fda5d-179">À l'aide d'un navigateur, accédez à l'adresse affichée dans le téléphone et saisissez votre nom d'utilisateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="fda5d-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Déploiement de téléphones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="fda5d-181">Entrez le code qui s'affiche sur le téléphone.</span><span class="sxs-lookup"><span data-stu-id="fda5d-181">Enter the code shown on the phone.</span></span>
    
     ![Déploiement de téléphones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="fda5d-183">Vérifiez que le site affiche "[nom du fabricant du téléphone] **Téléphone certifié Skype Entreprise**", et cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="fda5d-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**", and click **Continue**.</span></span>
    
     ![Déploiement de téléphones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="fda5d-185">Cliquez sur les informations de connexion de l'utilisateur ou sur **Use another account (Utiliser un autre compte)**:</span><span class="sxs-lookup"><span data-stu-id="fda5d-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Déploiement de téléphones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="fda5d-187">Lorsque la page suivante est affichée, vous pouvez fermer le navigateur en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="fda5d-187">Once below page is displayed, it is safe to close the browser.</span></span>
    
     ![Déploiement de téléphones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="fda5d-189">Les téléphones LPE pour Skype Entreprise Online prennent en charge la connexion via un périphérique USB uniquement.</span><span class="sxs-lookup"><span data-stu-id="fda5d-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="fda5d-190">**Déploiements pris en charge** Le tableau ci-après indique les types d'authentification pris en charge pour les modèles de déploiement actuellement pris en charge, y compris l'intégration d'Exchange, l'authentification moderne avec Multi-factor Authentication (MFA), et Skype Entreprise Online sur site.</span><span class="sxs-lookup"><span data-stu-id="fda5d-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fda5d-191">**Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="fda5d-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="fda5d-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="fda5d-192">**Exchange**</span></span> <br/> |<span data-ttu-id="fda5d-193">**Méthode de connexion au téléphone**</span><span class="sxs-lookup"><span data-stu-id="fda5d-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="fda5d-194">**Accès à Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="fda5d-194">**Skype For Business Access**</span></span> <br/> |<span data-ttu-id="fda5d-195">**Accès à Exchange avec Auth. moderne et MFA activées**</span><span class="sxs-lookup"><span data-stu-id="fda5d-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="fda5d-196">**Accès à Exchange avec Auth. moderne et MFA désactivées**</span><span class="sxs-lookup"><span data-stu-id="fda5d-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="fda5d-197">En ligne</span><span class="sxs-lookup"><span data-stu-id="fda5d-197">Online</span></span>  <br/> |<span data-ttu-id="fda5d-198">En ligne</span><span class="sxs-lookup"><span data-stu-id="fda5d-198">Online</span></span>  <br/> |<span data-ttu-id="fda5d-199">Connexion Web</span><span class="sxs-lookup"><span data-stu-id="fda5d-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="fda5d-200">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-200">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-201">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-201">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-202">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-202">Yes</span></span>  <br/> |
|<span data-ttu-id="fda5d-203">En ligne</span><span class="sxs-lookup"><span data-stu-id="fda5d-203">Online</span></span>  <br/> |<span data-ttu-id="fda5d-204">En ligne</span><span class="sxs-lookup"><span data-stu-id="fda5d-204">Online</span></span>  <br/> |<span data-ttu-id="fda5d-205">Nom d'utilisateur/Mot de passe</span><span class="sxs-lookup"><span data-stu-id="fda5d-205">Username/Password</span></span>  <br/> |<span data-ttu-id="fda5d-206">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-206">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-207">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-207">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-208">Non</span><span class="sxs-lookup"><span data-stu-id="fda5d-208">No</span></span>  <br/> |
|<span data-ttu-id="fda5d-209">En ligne</span><span class="sxs-lookup"><span data-stu-id="fda5d-209">Online</span></span>  <br/> |<span data-ttu-id="fda5d-210">Sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-210">On-premises</span></span>  <br/> |<span data-ttu-id="fda5d-211">Connexion Web</span><span class="sxs-lookup"><span data-stu-id="fda5d-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="fda5d-212">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-212">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-213">Non</span><span class="sxs-lookup"><span data-stu-id="fda5d-213">No</span></span>  <br/> |<span data-ttu-id="fda5d-214">Non</span><span class="sxs-lookup"><span data-stu-id="fda5d-214">No</span></span>  <br/> |
|<span data-ttu-id="fda5d-215">En ligne</span><span class="sxs-lookup"><span data-stu-id="fda5d-215">Online</span></span>  <br/> |<span data-ttu-id="fda5d-216">Sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-216">On-Premises</span></span>  <br/> |<span data-ttu-id="fda5d-217">Nom d'utilisateur/Mot de passe</span><span class="sxs-lookup"><span data-stu-id="fda5d-217">Username/Password</span></span>  <br/> |<span data-ttu-id="fda5d-218">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-218">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-219">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-219">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-220">Non</span><span class="sxs-lookup"><span data-stu-id="fda5d-220">No</span></span>  <br/> |
|<span data-ttu-id="fda5d-221">Sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-221">On-premises</span></span>  <br/> |<span data-ttu-id="fda5d-222">En ligne/sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="fda5d-223">Authentification par code confidentiel</span><span class="sxs-lookup"><span data-stu-id="fda5d-223">Pin Authentication</span></span>  <br/> |<span data-ttu-id="fda5d-224">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-224">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-225">Non</span><span class="sxs-lookup"><span data-stu-id="fda5d-225">No</span></span>  <br/> |<span data-ttu-id="fda5d-226">Non</span><span class="sxs-lookup"><span data-stu-id="fda5d-226">No</span></span>  <br/> |
|<span data-ttu-id="fda5d-227">Sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-227">On-premises</span></span>  <br/> |<span data-ttu-id="fda5d-228">En ligne/sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="fda5d-229">Nom d'utilisateur/Mot de passe</span><span class="sxs-lookup"><span data-stu-id="fda5d-229">Username/Password</span></span>  <br/> |<span data-ttu-id="fda5d-230">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-230">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-231">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-231">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-232">N/D</span><span class="sxs-lookup"><span data-stu-id="fda5d-232">N/A</span></span>  <br/> |
|<span data-ttu-id="fda5d-233">Sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-233">On-premises</span></span>  <br/> |<span data-ttu-id="fda5d-234">En ligne/sur site</span><span class="sxs-lookup"><span data-stu-id="fda5d-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="fda5d-235">Connexion via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="fda5d-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="fda5d-236">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-236">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-237">Oui</span><span class="sxs-lookup"><span data-stu-id="fda5d-237">Yes</span></span>  <br/> |<span data-ttu-id="fda5d-238">N/D</span><span class="sxs-lookup"><span data-stu-id="fda5d-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="fda5d-p116">**Fonctionnalités de téléphonie** Le jeu des fonctionnalités peut varier légèrement selon le partenaire de téléphonie IP. Pour le jeu complet des fonctionnalités et pour plus d’informations sur les fonctionnalités de chaque fabricant de téléphone, voir [Obtention de téléphones pour Skype Entreprise Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="fda5d-p116">**Phone features** The feature-set may slightly vary based on the IP phone partner. For complete feature set, see[Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) for more information on the features for each phone manufacturer.</span></span>
    
- <span data-ttu-id="fda5d-p117">**Phone-Lock** est une fonction récemment introduite dans les téléphones certifiés Skype Entreprise, qui est utilisée pour sécuriser un téléphone. Si elle est activée, les utilisateurs seront invités à créer un code confidentiel lors d'une authentification réussie. Une fois créé, les téléphones se verrouilleront lorsque le délai d'inactivité que vous aurez défini arrive à expiration, un utilisateur pourra verrouiller manuellement son téléphone, ou synchroniser le verrouillage de son téléphone avec son PC en utilisant le couplage de téléphone. Si le code confidentiel de verrouillage est saisi plusieurs fois de manière incorrecte, soit le téléphone déconnectera l'utilisateur, soit il demandera le code d'un administrateur pour déverrouiller le téléphone ; mais cela variera en fonction du partenaire de téléphonie. Le code confidentiel de l'utilisateur doit comprendre entre 6 et 15 chiffres.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successfully authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require a administrator's code to unlock the phone, but this will vary from depending on the phone Partner. The user's PIN should be between 6-15 digits.</span></span>
    
    <span data-ttu-id="fda5d-p118">Vous pouvez désactiver Phone-Lock (qui est activé par défaut) pour votre organisation, modifier le délai d'inactivité, et décider si les utilisateurs peuvent ou non passer des appels lorsqu'ils sont verrouillés, en utilisant les paramètres intrabande. Voir [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) pour plus de détails sur ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p118">You can disable Phone-Lock for your organization that is enabled by default, change the idle-timeout and choose if users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="fda5d-248">Étape 7 (facultative) : si vous disposez du couplage d'appareil et de Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="fda5d-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="fda5d-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="fda5d-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="fda5d-p119">BToE est un mécanisme de couplage pour les téléphones IP d'un partenaire, qui couple le téléphone d'un utilisateur avec son application Skype Entreprise Windows. BToE permet aux utilisateurs de :</span><span class="sxs-lookup"><span data-stu-id="fda5d-p119">BToE is a phone paining mechanism for Partner IP phones that pairs user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="fda5d-252">Se connecter à leur téléphone IP en utilisant leur application de bureau Skype Entreprise (sur un PC)</span><span class="sxs-lookup"><span data-stu-id="fda5d-252">Sign-into their IP phone using their Skype for Business desktop app (using a PC).</span></span>
    
- <span data-ttu-id="fda5d-253">Synchroniser Phone-Lock avec le verrouillage de leur PC</span><span class="sxs-lookup"><span data-stu-id="fda5d-253">Synchronize phone-lock with PC lock.</span></span>
    
- <span data-ttu-id="fda5d-254">Cliquer pour appeler</span><span class="sxs-lookup"><span data-stu-id="fda5d-254">Click to call.</span></span>
    
<span data-ttu-id="fda5d-p120">BToE peut être configuré pour fonctionner en deux modes :  *Auto*  (par défaut) et *Manuel*. Il peut également être activé (par défaut)/désactivé pour les utilisateurs utilisant les paramètres intrabande de Skype Entreprise. Lorsqu'ils travaillent en mode *Manuel*, les utilisateurs devront effectuer une étape supplémentaire pour coupler leur téléphone avec leur application Windows.</span><span class="sxs-lookup"><span data-stu-id="fda5d-p120">BToE can be configured to operate in 2 modes;  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="fda5d-258">**Pour déployer BToE pour les utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="fda5d-258">**** To deploy BToE to users</span></span>
  
1. <span data-ttu-id="fda5d-259">Connectez leur PC à leur téléphone à l'aide du port du PC.</span><span class="sxs-lookup"><span data-stu-id="fda5d-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Déploiement de téléphones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="fda5d-p121">Téléchargez et installez la dernière version du logiciel BToE à partir du site Web du fabricant disponible en cliquant sur les liens ci-dessous. Pour une expérience utilisateur optimale, vous pouvez distribuer et installer le logiciel BToE à l'aide d'une solution de distribution d'administrateur, telle que System Center Configuration Manager (SCCM). Pour obtenir de l'aide pour utiliser SCCM, reportez-vous à la page [Packages et programmes dans System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="fda5d-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="fda5d-264">Site de téléchargement du logiciel BToE Polycom</span><span class="sxs-lookup"><span data-stu-id="fda5d-264">Polycom BToE Software Download site:</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="fda5d-265">Téléchargement du logiciel BToE pour Yealink</span><span class="sxs-lookup"><span data-stu-id="fda5d-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="fda5d-266">Téléchargement du logiciel BToE pour AudioCodes</span><span class="sxs-lookup"><span data-stu-id="fda5d-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="fda5d-267">Le paramètre du serveur pour BToE est défini par défaut comme **Activé** et **Mode auto**.</span><span class="sxs-lookup"><span data-stu-id="fda5d-267">The server setting for BToE is set to Enabled and Auto mode by default, to change those settings, seeSet-CsIPPhonePolicy.</span></span> <span data-ttu-id="fda5d-268">Pour modifier ces paramètres, voir [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="fda5d-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="fda5d-269">BToE n'est pas actuellement supporté sur les plates-formes Mac et VDI.</span><span class="sxs-lookup"><span data-stu-id="fda5d-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="fda5d-270">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="fda5d-270">Related topics</span></span>
[<span data-ttu-id="fda5d-271">Obtention de numéros de téléphone de service pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fda5d-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="fda5d-272">Ce dont vous disposerez avec le Système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="fda5d-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="fda5d-273">Disponibilité par pays et par région de l'Audioconférence et des Plans d'appels</span><span class="sxs-lookup"><span data-stu-id="fda5d-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
