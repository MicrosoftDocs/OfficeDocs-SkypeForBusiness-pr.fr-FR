---
title: Configurer l’authentification à deux facteurs dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Résumé : Configurez l’authentification à deux facteurs dans Skype Entreprise Server.'
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814414"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="eabf1-103">Configurer l’authentification à deux facteurs dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eabf1-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="eabf1-104">**Résumé :** Configurez l’authentification à deux facteurs dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="eabf1-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="eabf1-105">Les sections suivantes décrivent les étapes nécessaires pour configurer l’authentification à deux facteurs pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="eabf1-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="eabf1-106">Pour plus d’informations sur l’authentification à deux facteurs, voir Activation de [l’authentification multifacteur Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)pour les administrateurs en ligne - Grid User Post .</span><span class="sxs-lookup"><span data-stu-id="eabf1-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="eabf1-107">Configurer une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="eabf1-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="eabf1-108">Les étapes suivantes décrivent comment configurer une ca racine d’entreprise pour prendre en charge l’authentification par carte à puce :</span><span class="sxs-lookup"><span data-stu-id="eabf1-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="eabf1-109">Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, voir Installer une autorité de certification racine [d’entreprise.](https://go.microsoft.com/fwlink/p/?LinkID=313364)</span><span class="sxs-lookup"><span data-stu-id="eabf1-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="eabf1-110">Connectez-vous à l’ordinateur de l’ac d’entreprise à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="eabf1-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="eabf1-111">Lancez system Manager et vérifiez que le rôle d’inscription web de l’autorité de certification est installé.</span><span class="sxs-lookup"><span data-stu-id="eabf1-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="eabf1-112">Dans le menu **Outils d’administration,** ouvrez la console de gestion **de l’autorité** de certification.</span><span class="sxs-lookup"><span data-stu-id="eabf1-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="eabf1-113">Dans le volet de navigation, développez **Autorité de certification.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="eabf1-114">Cliquez avec le bouton **droit sur Modèles de certificats,** **sélectionnez Nouveau,** puis **sélectionnez Modèle de certificat à émettre.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="eabf1-115">Sélectionnez **Agent d’inscription,** **Utilisateur de** carte à puce et Logo par carte **à puce.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="eabf1-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eabf1-116">Click **OK**.</span></span>

8. <span data-ttu-id="eabf1-117">Cliquez avec le bouton droit **sur Modèles de certificats.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="eabf1-118">Sélectionnez **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="eabf1-118">Select **Manage**.</span></span>

10. <span data-ttu-id="eabf1-119">Ouvrez les propriétés du modèle Utilisateur à puce.</span><span class="sxs-lookup"><span data-stu-id="eabf1-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="eabf1-120">Cliquez sur **l’onglet** Sécurité.</span><span class="sxs-lookup"><span data-stu-id="eabf1-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="eabf1-121">Modifiez les autorisations comme suit :</span><span class="sxs-lookup"><span data-stu-id="eabf1-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="eabf1-122">Ajouter des comptes AD d’utilisateur individuels avec des autorisations de lecture/inscription (autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="eabf1-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="eabf1-123">Ajouter un groupe de sécurité contenant des utilisateurs de carte à puce avec des autorisations de lecture/inscription (autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="eabf1-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="eabf1-124">Ajouter le groupe Utilisateurs du domaine avec des autorisations de lecture/inscription (autoriser)</span><span class="sxs-lookup"><span data-stu-id="eabf1-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="eabf1-125">Configurer Windows 8 pour les cartes à puce virtuelles</span><span class="sxs-lookup"><span data-stu-id="eabf1-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="eabf1-126">Un facteur à prendre en compte lors du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce est le coût d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="eabf1-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="eabf1-127">Windows 8 offre un certain nombre de nouvelles fonctionnalités de sécurité, et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.</span><span class="sxs-lookup"><span data-stu-id="eabf1-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="eabf1-128">Pour les ordinateurs équipés d’une puce de module de plateforme de confiance (TPM) qui répond aux spécifications de la version 1.2, les organisations peuvent désormais profiter des avantages de l’accès par carte à puce sans effectuer d’investissements supplémentaires en matériel.</span><span class="sxs-lookup"><span data-stu-id="eabf1-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="eabf1-129">Pour plus d’informations, [voir Utilisation de cartes à puce virtuelles avec Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)</span><span class="sxs-lookup"><span data-stu-id="eabf1-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="eabf1-130">Pour configurer Windows 8 pour les cartes à puce virtuelles</span><span class="sxs-lookup"><span data-stu-id="eabf1-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="eabf1-131">Connectez-vous à l’ordinateur Windows 8 à l’aide des informations d’identification d’un utilisateur activé pour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eabf1-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="eabf1-132">Dans l’écran d’accueil de Windows 8, déplacez votre curseur dans le coin inférieur droit de l’écran.</span><span class="sxs-lookup"><span data-stu-id="eabf1-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="eabf1-133">Sélectionnez **l’option** Rechercher, puis recherchezCommand Prompt.</span><span class="sxs-lookup"><span data-stu-id="eabf1-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="eabf1-134">Cliquez avec le bouton droit **sur l’invite de** commandes, puis **sélectionnez Exécuter en tant qu’administrateur.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="eabf1-135">Ouvrez la console de gestion du module de plateforme fiable (TPM) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```console
  Tpm.msc
  ```

6. <span data-ttu-id="eabf1-136">À partir de la console de gestion du TPM, vérifiez que la version de spécification du TPM est au moins 1.2</span><span class="sxs-lookup"><span data-stu-id="eabf1-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="eabf1-137">Si vous recevez une boîte de dialogue indiquant qu’un module de plateforme de confiance (TPM) compatible est incohable, vérifiez que l’ordinateur dispose d’un module TPM compatible et qu’il est activé dans le BIOS système.</span><span class="sxs-lookup"><span data-stu-id="eabf1-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="eabf1-138">Fermer la console de gestion du TPM</span><span class="sxs-lookup"><span data-stu-id="eabf1-138">Close the TPM management console</span></span>

8. <span data-ttu-id="eabf1-139">À partir de l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="eabf1-140">Pour fournir une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez /pin prompt à la place.</span><span class="sxs-lookup"><span data-stu-id="eabf1-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="eabf1-141">À partir de l’invite de commandes, ouvrez la console gestion de l’ordinateur en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```console
  CompMgmt.msc
  ```

10. <span data-ttu-id="eabf1-142">Dans la console gestion de l’ordinateur, sélectionnez **Gestion des périphériques.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="eabf1-143">Développez **les lecteurs de carte à puce.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="eabf1-144">Vérifiez que le nouveau lecteur de carte à puce virtuel a bien été créé.</span><span class="sxs-lookup"><span data-stu-id="eabf1-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="eabf1-145">Inscrire des utilisateurs pour l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="eabf1-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="eabf1-146">Il existe généralement deux méthodes pour inscrire des utilisateurs pour l’authentification par carte à puce.</span><span class="sxs-lookup"><span data-stu-id="eabf1-146">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="eabf1-147">La méthode la plus simple consiste à faire en sorte que les utilisateurs s’inscrivent directement pour l’authentification par carte à puce à l’aide de l’inscription web, tandis que la méthode la plus complexe implique l’utilisation d’un agent d’inscription.</span><span class="sxs-lookup"><span data-stu-id="eabf1-147">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="eabf1-148">Cette rubrique se concentre sur l’inscription automatique pour les certificats de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="eabf1-148">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="eabf1-149">Pour plus d’informations sur l’inscription au nom des utilisateurs en tant qu’agent d’inscription, voir s’inscrire pour les certificats de la part [d’autres utilisateurs.](https://go.microsoft.com/fwlink/p/?LinkID=313367)</span><span class="sxs-lookup"><span data-stu-id="eabf1-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="eabf1-150">Pour inscrire des utilisateurs pour l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="eabf1-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="eabf1-151">Connectez-vous à la station de travail Windows 8 à l’aide des informations d’identification d’un utilisateur activé pour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eabf1-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="eabf1-152">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="eabf1-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="eabf1-153">Accédez à la page **Inscription web de l’autorité** de certification (par exemple, https://MyCA.contoso.com/certsrv) .</span><span class="sxs-lookup"><span data-stu-id="eabf1-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="eabf1-154">Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="eabf1-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="eabf1-155">Dans la page **d’accueil,** **sélectionnez Demander un certificat.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="eabf1-156">Ensuite, sélectionnez **Demande avancée.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="eabf1-157">Sélectionnez **Créer et envoyer une demande à cette ca.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="eabf1-158">Sélectionnez **Utilisateur de carte à puce** sous la section Modèle **de** certificat et terminez la demande de certificat avancée avec les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="eabf1-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="eabf1-159">**Les options clés** confirment qu’il suit les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="eabf1-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="eabf1-160">Sélectionnez la **bouton d’radio Créer un jeu de** touches</span><span class="sxs-lookup"><span data-stu-id="eabf1-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="eabf1-161">Pour **le fournisseur CSP,** sélectionnez **Microsoft Base Smart Card Crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="eabf1-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="eabf1-162">Pour **l’utilisation de** la clé, **sélectionnez Exchange** (il s’agit de la seule option disponible).</span><span class="sxs-lookup"><span data-stu-id="eabf1-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="eabf1-163">For **Key Size**, enter 2048</span><span class="sxs-lookup"><span data-stu-id="eabf1-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="eabf1-164">Confirmer que **le nom du conteneur de la** clé automatique est sélectionné</span><span class="sxs-lookup"><span data-stu-id="eabf1-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="eabf1-165">Laissez les autres cases désactivées.</span><span class="sxs-lookup"><span data-stu-id="eabf1-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="eabf1-166">Sous **Options supplémentaires,** confirmez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="eabf1-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="eabf1-167">For **Request Format** select **CMC**.</span><span class="sxs-lookup"><span data-stu-id="eabf1-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="eabf1-168">Pour **l’algorithme de** hachage, **sélectionnez sha1**.</span><span class="sxs-lookup"><span data-stu-id="eabf1-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="eabf1-169">For **Friendly Name** enterSmardcard Certificate.</span><span class="sxs-lookup"><span data-stu-id="eabf1-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="eabf1-170">Si vous utilisez un lecteur de carte à puce physique, insérez la carte à puce dans l’appareil.</span><span class="sxs-lookup"><span data-stu-id="eabf1-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="eabf1-171">Cliquez **sur Envoyer** pour envoyer la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="eabf1-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="eabf1-172">Lorsque vous y invitez, entrez le code confidentiel qui a été utilisé pour créer la carte à puce virtuelle.</span><span class="sxs-lookup"><span data-stu-id="eabf1-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eabf1-173">La valeur par défaut du code confidentiel de carte à puce virtuelle est « 12345678 ».</span><span class="sxs-lookup"><span data-stu-id="eabf1-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="eabf1-174">Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer le processus d’inscription.</span><span class="sxs-lookup"><span data-stu-id="eabf1-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="eabf1-175">Si votre demande de certificat échoue avec l’erreur « Ce navigateur Web ne prend pas en charge la génération des demandes de certificat », il existe trois façons de résoudre le problème :</span><span class="sxs-lookup"><span data-stu-id="eabf1-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="eabf1-176">Configurer les services de fédération Active Directory (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="eabf1-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="eabf1-177">La section suivante décrit comment configurer les services de fédération Active Directory (AD FS 2.0) pour prendre en charge l’authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="eabf1-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="eabf1-178">Pour plus d’informations sur l’installation d’AD FS 2.0, voir [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="eabf1-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="eabf1-179">Lors de l’installation d’AD FS 2.0, n’utilisez pas le Gestionnaire de serveur Windows pour ajouter le rôle Services de fédération Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eabf1-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="eabf1-180">Téléchargez et installez plutôt le [package Active Directory Federation Services 2.0 RTW.](https://go.microsoft.com/fwlink/p/?LinkId=313375)</span><span class="sxs-lookup"><span data-stu-id="eabf1-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="eabf1-181">Pour configurer AD FS pour l’authentification à deux facteurs</span><span class="sxs-lookup"><span data-stu-id="eabf1-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="eabf1-182">Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="eabf1-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="eabf1-183">Démarrez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eabf1-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="eabf1-184">À partir Windows PowerShell ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="eabf1-185">Établissez un partenariat avec chaque serveur qui sera activé pour l’authentification passive en exécutant la commande suivante, en remplaçant le nom du serveur spécifique à votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="eabf1-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="eabf1-186">Dans le menu Outils d’administration, lancez la console de gestion AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="eabf1-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="eabf1-187">Développez **les relations**  >  **d’confiance des relations de confiance.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="eabf1-188">Vérifiez qu’une nouvelle confiance a été créée pour votre serveur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eabf1-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="eabf1-189">Créez et affectez une règle d’autorisation d’émission pour votre approbation de partie de confiance à l’Windows PowerShell en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="eabf1-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="eabf1-190">Créez et affectez une règle de transformation d’émission pour votre confiance de partie de confiance à l’Windows PowerShell en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="eabf1-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="eabf1-191">Dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur votre confiance de partie de confiance et sélectionnez **Modifier les règles de revendication.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="eabf1-192">Sélectionnez **l’onglet Règles d’autorisation** d’émission et vérifiez que la nouvelle règle d’autorisation a été correctement créée.</span><span class="sxs-lookup"><span data-stu-id="eabf1-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="eabf1-193">Sélectionnez **l’onglet Règles de** transformation d’émission et vérifiez que la nouvelle règle de transformation a été correctement créée.</span><span class="sxs-lookup"><span data-stu-id="eabf1-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="eabf1-194">Configuration d’AD FS 2.0 pour prendre en charge l’authentification client</span><span class="sxs-lookup"><span data-stu-id="eabf1-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="eabf1-195">Il existe deux types d’authentification possibles qui peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :</span><span class="sxs-lookup"><span data-stu-id="eabf1-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="eabf1-196">Authentification basée sur les formulaires (FBA)</span><span class="sxs-lookup"><span data-stu-id="eabf1-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="eabf1-197">Authentification du client transport Layer Security</span><span class="sxs-lookup"><span data-stu-id="eabf1-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="eabf1-198">À l’aide de l’authentification basée sur les formulaires, vous pouvez développer une page web qui permet aux utilisateurs de s’authentifier à l’aide de leur nom d’utilisateur/mot de passe ou de leur carte à puce et de leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="eabf1-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="eabf1-199">Cette rubrique se concentre sur l’implémenter l’authentification client de couche transport avec AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="eabf1-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="eabf1-200">Pour plus d’informations sur les types d’authentification AD FS 2.0, voir [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="eabf1-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="eabf1-201">Pour configurer AD FS 2.0 pour prendre en charge l’authentification client</span><span class="sxs-lookup"><span data-stu-id="eabf1-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="eabf1-202">Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="eabf1-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="eabf1-203">Lancez l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="eabf1-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="eabf1-204">Accédez à C:\inetpub\adfs\ls</span><span class="sxs-lookup"><span data-stu-id="eabf1-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="eabf1-205">Effectuer une copie de sauvegarde du fichier web.config existant.</span><span class="sxs-lookup"><span data-stu-id="eabf1-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="eabf1-206">Ouvrez le fichier web.config à l’aide du Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="eabf1-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="eabf1-207">Dans la barre de menus, **sélectionnez Modifier,** puis **Rechercher.**</span><span class="sxs-lookup"><span data-stu-id="eabf1-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="eabf1-208">Recherchez \<localAuthenticationTypes\> .</span><span class="sxs-lookup"><span data-stu-id="eabf1-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="eabf1-209">Notez que quatre types d’authentification sont répertoriés, un par ligne.</span><span class="sxs-lookup"><span data-stu-id="eabf1-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="eabf1-210">Déplacez la ligne contenant le type d’authentification TLSClient en haut de la liste dans la section.</span><span class="sxs-lookup"><span data-stu-id="eabf1-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="eabf1-211">Enregistrez et fermez web.config fichier.</span><span class="sxs-lookup"><span data-stu-id="eabf1-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="eabf1-212">Lancez une invite de commandes avec des privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="eabf1-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="eabf1-213">Redémarrez les services Internet (IIS) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-213">Restart IIS by running the following command:</span></span>

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="eabf1-214">Configuration de l’authentification passive Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eabf1-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="eabf1-215">La section suivante décrit comment configurer Skype Entreprise Server pour prendre en charge l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="eabf1-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="eabf1-216">Une fois activé, les utilisateurs qui sont activés pour l’authentification à deux facteurs doivent utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eabf1-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="eabf1-217">Il est vivement recommandé que les clients activent l’authentification passive pour le serveur d’inscriptions et les services Web au niveau du service.</span><span class="sxs-lookup"><span data-stu-id="eabf1-217">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="eabf1-218">Si l’authentification passive est activée pour le serveur d’inscriptions et les services Web au niveau global, elle entraîne probablement des échecs d’authentification à l’échelle de l’organisation pour les utilisateurs qui ne se sont pas signés avec le client de bureau pris en charge.</span><span class="sxs-lookup"><span data-stu-id="eabf1-218">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="eabf1-219">Web Service Configuration</span><span class="sxs-lookup"><span data-stu-id="eabf1-219">Web Service Configuration</span></span>

<span data-ttu-id="eabf1-220">Les étapes suivantes décrivent comment créer une configuration de service web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="eabf1-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="eabf1-221">Pour créer une configuration de service web personnalisée</span><span class="sxs-lookup"><span data-stu-id="eabf1-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="eabf1-222">Connectez-vous à votre serveur frontal Skype Entreprise Server à l’aide d’un compte d’administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eabf1-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="eabf1-223">Lancez Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="eabf1-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="eabf1-224">À partir de la ligne de commande Skype Entreprise Server Management Shell, créez une configuration de service Web pour chaque directeur, pool d’entreprise et serveur Standard Edition qui sera activé pour l’authentification passive en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="eabf1-225">La valeur du nom de domaine complet WsFedPassiveMetadataUri est le nom de service de fédération de votre serveur AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="eabf1-225">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="eabf1-226">La valeur Nom du service de fédération se trouve dans la console de gestion AD FS 2.0 en cliquant avec le bouton droit sur **Service** dans le volet de navigation, puis en sélectionnant Modifier les propriétés du **service** de fédération.</span><span class="sxs-lookup"><span data-stu-id="eabf1-226">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="eabf1-227">Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été définies correctement en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="eabf1-228">Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification webticket.</span><span class="sxs-lookup"><span data-stu-id="eabf1-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="eabf1-229">Pour tous les directeurs, pools d’entreprise et serveurs Standard Edition qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans les services Web Skype Entreprise en exécutant l’applet de la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="eabf1-230">Vérifiez que tous les autres types d’authentification ont été correctement désactivés en exécutant l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="eabf1-231">Proxy Configuration</span><span class="sxs-lookup"><span data-stu-id="eabf1-231">Proxy Configuration</span></span>

<span data-ttu-id="eabf1-232">Lorsque l’authentification par certificat est désactivée pour les services Web Skype Entreprise, le client Skype Entreprise utilise un type d’authentification moins privilégié, tel que Kerberos ou NTLM, pour s’authentifier auprès du service serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="eabf1-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="eabf1-233">L’authentification par certificat est toujours nécessaire pour permettre au client de récupérer un site webticket. Toutefois, Kerberos et NTLM doivent être désactivés pour le service serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="eabf1-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="eabf1-234">Les étapes suivantes décrivent comment créer une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="eabf1-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="eabf1-235">Pour créer une configuration de proxy personnalisée</span><span class="sxs-lookup"><span data-stu-id="eabf1-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="eabf1-236">À partir de la ligne de commande Skype Entreprise Server Management Shell, créez une configuration de proxy pour chaque pool Edge Skype Entreprise Server, pool d’entreprise et serveur Standard Edition qui sera activé pour l’authentification passive en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="eabf1-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="eabf1-237">Vérifiez que tous les autres types d’authentification proxy ont été correctement désactivés en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eabf1-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="eabf1-238">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eabf1-238">See also</span></span>

[<span data-ttu-id="eabf1-239">Gérer l’authentification à deux facteurs dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eabf1-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="eabf1-240">Utiliser l’authentification à deux facteurs avec le client Skype Entreprise et Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eabf1-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
