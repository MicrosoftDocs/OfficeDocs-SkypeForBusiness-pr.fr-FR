---
title: Configurer l’authentification à deux facteurs dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 'Résumé: configuration de l’authentification à deux facteurs dans Skype entreprise Server.'
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283839"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="1fd31-103">Configurer l’authentification à deux facteurs dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1fd31-103">Configure two-factor authentication in Skype for Business Server</span></span>

<span data-ttu-id="1fd31-104">**Résumé:** Configurer l’authentification à deux facteurs dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1fd31-104">**Summary:** Configure two-factor authentication in Skype for Business Server.</span></span>

<span data-ttu-id="1fd31-105">Les sections ci-dessous décrivent la procédure de configuration de l’authentification à deux facteurs pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1fd31-105">The following sections describe the steps necessary to configure two-factor authentication for your deployment.</span></span> <span data-ttu-id="1fd31-106">Pour plus d’informations sur l’authentification à deux facteurs, voir [activation de l’authentification multifacteur Office 365 pour les administrateurs en ligne](https://go.microsoft.com/fwlink/p/?LinkId=313332)</span><span class="sxs-lookup"><span data-stu-id="1fd31-106">For more information about Two-factor authentication, see [Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332).</span></span>

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="1fd31-107">Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="1fd31-107">Configure an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="1fd31-108">La procédure ci-dessous décrit la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :</span><span class="sxs-lookup"><span data-stu-id="1fd31-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

<span data-ttu-id="1fd31-109">Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, voir [installer une autorité de certification racine d’entreprise](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span><span class="sxs-lookup"><span data-stu-id="1fd31-109">For information on how to install an Enterprise Root CA, see [Install an Enterprise Root Certification Authority](https://go.microsoft.com/fwlink/p/?LinkID=313364).</span></span>

1. <span data-ttu-id="1fd31-110">Connectez-vous à l’ordinateur de l’autorité de certification d’entreprise à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="1fd31-110">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="1fd31-111">Lancez le gestionnaire système, puis vérifiez que le rôle Inscription de l’autorité de certification par le biais du web est installé.</span><span class="sxs-lookup"><span data-stu-id="1fd31-111">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3. <span data-ttu-id="1fd31-112">Dans le menu **Outils d’administration**, ouvrez la console de gestion **Autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-112">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4. <span data-ttu-id="1fd31-113">Dans le volet de navigation, développez **Autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-113">In the Navigation pane, expand **Certification Authority**.</span></span>

5. <span data-ttu-id="1fd31-114">Cliquez avec le bouton droit sur **Modèles de certificat**, sélectionnez **Nouveau**, puis **Modèle de certificat à délivrer**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-114">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6. <span data-ttu-id="1fd31-115">Sélectionnez **Agent d’inscription**, **Utilisateur de carte à puce** et **Connexion par carte à puce**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-115">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7. <span data-ttu-id="1fd31-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-116">Click **OK**.</span></span>

8. <span data-ttu-id="1fd31-117">Cliquez avec le bouton droit sur **Modèles de certificat**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-117">Right click on **Certificate Templates**.</span></span>

9. <span data-ttu-id="1fd31-118">Sélectionnez **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-118">Select **Manage**.</span></span>

10. <span data-ttu-id="1fd31-119">Ouvrez les propriétés du modèle utilisateur de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="1fd31-119">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="1fd31-120">Cliquez sur l’onglet **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-120">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="1fd31-121">Modifiez les autorisations, comme suit :</span><span class="sxs-lookup"><span data-stu-id="1fd31-121">Change the permissions as follows:</span></span>

    - <span data-ttu-id="1fd31-122">Ajoutez des comptes Active Directory d’utilisateurs individuels avec les autorisations Lire/Inscrire (Autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="1fd31-122">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="1fd31-123">Ajoutez un groupe de sécurité contenant des utilisateurs de carte à puce avec les autorisations Lire/Inscrire (Autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="1fd31-123">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>

    - <span data-ttu-id="1fd31-124">Ajoutez le groupe Utilisateurs du domaine avec les autorisations Lire/Inscrire (Autoriser).</span><span class="sxs-lookup"><span data-stu-id="1fd31-124">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

## <a name="configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="1fd31-125">Configuration de Windows 8 pour les cartes à puce virtuelles</span><span class="sxs-lookup"><span data-stu-id="1fd31-125">Configure Windows 8 for Virtual Smart Cards</span></span>

<span data-ttu-id="1fd31-126">Le coût de mise en œuvre est l’un des facteurs à prendre en compte dans le cadre du déploiement de l’authentification à deux facteurs et de la technologie de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="1fd31-126">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="1fd31-127">Windows 8 fournit un certain nombre de nouvelles fonctionnalités de sécurité et l’une des nouvelles fonctionnalités les plus intéressantes est la prise en charge des cartes à puce virtuelles.</span><span class="sxs-lookup"><span data-stu-id="1fd31-127">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="1fd31-128">Pour les ordinateurs équipés d’une puce de module de plateforme sécurisée conforme à la spécification version 1.2, les organisations peuvent désormais tirer parti des avantages d’une ouverture de session par carte à puce sans investissement matériel supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1fd31-128">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="1fd31-129">Pour plus d’informations, reportez-vous [à la rubrique utilisation de cartes à puce virtuelles avec Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span><span class="sxs-lookup"><span data-stu-id="1fd31-129">For more information, see [Using Virtual Smart Cards with Windows 8](https://go.microsoft.com/fwlink/p/?LinkId=313365).</span></span>

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="1fd31-130">Configuration de Windows 8 pour les cartes à puce virtuelles</span><span class="sxs-lookup"><span data-stu-id="1fd31-130">To Configure Windows 8 for Virtual Smart Cards</span></span>

1. <span data-ttu-id="1fd31-131">Connectez-vous à l’ordinateur Windows 8 à l’aide des informations d’identification d’un utilisateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1fd31-131">Log in to the Windows 8 computer using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="1fd31-132">Dans l’écran d’accueil de Windows 8, déplacez votre curseur dans le coin droit inférieur de l’écran.</span><span class="sxs-lookup"><span data-stu-id="1fd31-132">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3. <span data-ttu-id="1fd31-133">Sélectionnez l’option **Rechercher** , puis cliquez sur Rechercher forCommand invite.</span><span class="sxs-lookup"><span data-stu-id="1fd31-133">Select the **Search** option, and then search forCommand Prompt.</span></span>

4. <span data-ttu-id="1fd31-134">Cliquez avec le bouton droit sur **Invite de commandes**, puis sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-134">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5. <span data-ttu-id="1fd31-135">Ouvrez la console de gestion du module de plateforme sécurisée en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-135">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>

  ```
  Tpm.msc
  ```

6. <span data-ttu-id="1fd31-136">À partir de la console de gestion du module de plateforme sécurisée, vérifiez que la spécification du module de plateforme sécurisée correspond à la version 1.2 au minimum.</span><span class="sxs-lookup"><span data-stu-id="1fd31-136">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>

    > [!NOTE]
    > <span data-ttu-id="1fd31-137">Si un message indiquant qu’aucun module de plateforme sécurisée compatible n’a été trouvé, vérifiez que l’ordinateur dispose d’un module de plateforme sécurisée compatible et que celui-ci est activé dans le BIOS système.</span><span class="sxs-lookup"><span data-stu-id="1fd31-137">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

7. <span data-ttu-id="1fd31-138">Fermez la console de gestion du module de plateforme sécurisée.</span><span class="sxs-lookup"><span data-stu-id="1fd31-138">Close the TPM management console</span></span>

8. <span data-ttu-id="1fd31-139">Dans l’invite de commandes, créez une carte à puce virtuelle à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-139">From the command prompt, create a new virtual smart card using the following command:</span></span>

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > <span data-ttu-id="1fd31-140">Pour indiquer une valeur de code confidentiel personnalisée lors de la création de la carte à puce virtuelle, utilisez plutôt l’invite /pin.</span><span class="sxs-lookup"><span data-stu-id="1fd31-140">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

9. <span data-ttu-id="1fd31-141">Dans l’invite de commandes, ouvrez la console de gestion de l’ordinateur en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-141">From the command prompt, open the Computer Management console by running the following command:</span></span>

  ```
  CompMgmt.msc
  ```

10. <span data-ttu-id="1fd31-142">Dans la console de gestion de l’ordinateur, sélectionnez **Gestion des périphériques**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-142">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="1fd31-143">Développez **Lecteurs de cartes à puce**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-143">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="1fd31-144">Vérifiez que le lecteur de cartes à puce virtuelles a bien été créé.</span><span class="sxs-lookup"><span data-stu-id="1fd31-144">Verify that the new virtual smart card reader has been created successfully.</span></span>

## <a name="enroll-users-for-smart-card-authentication"></a><span data-ttu-id="1fd31-145">Inscription d’utilisateurs pour l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="1fd31-145">Enroll users for smart card authentication</span></span>

<span data-ttu-id="1fd31-p104">Deux méthodes permettent d’inscrire les utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire s’inscrire directement les utilisateurs pour l’authentification par carte à puce par l’inscription par le biais du web. La méthode la plus complexe implique d’utiliser un agent d’inscription. Cette rubrique décrit l’inscription automatique pour les certificats de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="1fd31-p104">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="1fd31-149">Pour plus d’informations sur l’inscription au nom des utilisateurs en tant qu’agent d’inscription, voir [inscrire des certificats pour le compte d’autres utilisateurs](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span><span class="sxs-lookup"><span data-stu-id="1fd31-149">For more information on enrolling on behalf of users as an enrollment agent, see [Enroll for Certificates on Behalf of Other Users](https://go.microsoft.com/fwlink/p/?LinkID=313367).</span></span>

### <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="1fd31-150">Inscription des utilisateurs pour l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="1fd31-150">To Enroll Users for Smart Card Authentication</span></span>

1. <span data-ttu-id="1fd31-151">Connectez-vous à la station de travail Windows 8 en utilisant les informations d’identification d’un utilisateur compatible Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1fd31-151">Log in to the Windows 8 workstation using the credentials of a Skype for Business-enabled user.</span></span>

2. <span data-ttu-id="1fd31-152">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="1fd31-152">Launch Internet Explorer.</span></span>

3. <span data-ttu-id="1fd31-153">Accédez à la page d’inscription sur le Web de l' **autorité** de https://MyCA.contoso.com/certsrv)certification (par exemple,.</span><span class="sxs-lookup"><span data-stu-id="1fd31-153">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1fd31-154">Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="1fd31-154">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

4. <span data-ttu-id="1fd31-155">Dans la page **Bienvenue**, sélectionnez **Demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-155">On the **Welcome** Page, select **Request a certificate**.</span></span>

5. <span data-ttu-id="1fd31-156">Sélectionnez ensuite **Demande avancée**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-156">Next, select **Advanced Request**.</span></span>

6. <span data-ttu-id="1fd31-157">Sélectionnez **Créer et envoyer une demande de requête auprès de cette autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-157">Select **Create and submit a request to this CA**.</span></span>

7. <span data-ttu-id="1fd31-158">Sélectionnez **Utilisateur de carte à puce** sous la section **Modèle de certificat**, puis remplissez la demande de certificat avancée avec les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fd31-158">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>

  - <span data-ttu-id="1fd31-159">Sous **Options des clés**, vérifiez que les paramètres suivants sont sélectionnés :</span><span class="sxs-lookup"><span data-stu-id="1fd31-159">**Key Options** confirm he following settings:</span></span>

    - <span data-ttu-id="1fd31-160">Sélectionnez la case d’option **Créer un jeu de clés**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-160">Select the **Create new key set** radio button</span></span>

    - <span data-ttu-id="1fd31-161">Dans **Fournisseur de services de chiffrement**, sélectionnez **Fournisseur de services de chiffrement Microsoft pour carte à puce**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-161">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>

    - <span data-ttu-id="1fd31-162">Dans **Utilisation de la clé**, sélectionnez **Exchange** (seule option disponible).</span><span class="sxs-lookup"><span data-stu-id="1fd31-162">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>

    - <span data-ttu-id="1fd31-163">Dans **Taille de la clé**, entrez 2048.</span><span class="sxs-lookup"><span data-stu-id="1fd31-163">For **Key Size**, enter 2048</span></span>

    - <span data-ttu-id="1fd31-164">Vérifiez que l’option **Nom de conteneur de clé automatique** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1fd31-164">Confirm that **Automatic key container name** is selected</span></span>

    - <span data-ttu-id="1fd31-165">Laissez les autres cases à cocher désactivées.</span><span class="sxs-lookup"><span data-stu-id="1fd31-165">Leave the other boxes unchecked.</span></span>

  - <span data-ttu-id="1fd31-166">Sous **Options supplémentaires**, vérifiez que les valeurs suivantes sont sélectionnées :</span><span class="sxs-lookup"><span data-stu-id="1fd31-166">Under **Additional Options** confirm the following values:</span></span>

    - <span data-ttu-id="1fd31-167">Dans **Format de la demande**, sélectionnez **CMC**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-167">For **Request Format** select **CMC**.</span></span>

    - <span data-ttu-id="1fd31-168">Dans **Algorithme de hachage**, sélectionnez **sha1**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-168">For **Hash Algorithm** select **sha1**.</span></span>

    - <span data-ttu-id="1fd31-169">Pour **nom convivial** enterSmardcard certificat.</span><span class="sxs-lookup"><span data-stu-id="1fd31-169">For **Friendly Name** enterSmardcard Certificate.</span></span>

8. <span data-ttu-id="1fd31-170">Si vous utilisez un lecteur de cartes à puces physiques, insérez la carte à puce dans l’appareil.</span><span class="sxs-lookup"><span data-stu-id="1fd31-170">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9. <span data-ttu-id="1fd31-171">Cliquez sur **Envoyer** pour envoyer la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="1fd31-171">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="1fd31-172">Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.</span><span class="sxs-lookup"><span data-stu-id="1fd31-172">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1fd31-173">La valeur du code confidentiel de carte à puce virtuelle par défaut est «12345678».</span><span class="sxs-lookup"><span data-stu-id="1fd31-173">The default virtual smart card PIN value is '12345678'.</span></span>

11. <span data-ttu-id="1fd31-174">Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer la procédure d’inscription.</span><span class="sxs-lookup"><span data-stu-id="1fd31-174">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1fd31-175">Si votre demande de certificat échoue avec l’erreur «ce navigateur Web ne prend pas en charge la génération de demandes de certificat», il existe trois façons de résoudre le problème:</span><span class="sxs-lookup"><span data-stu-id="1fd31-175">If your certificate request fails with the error "This Web browser does not support the generation of certificate requests," there are three possible ways to resolve the issue:</span></span>

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a><span data-ttu-id="1fd31-176">Configuration d’Active Directory Federation Services (AD FS 2.0)</span><span class="sxs-lookup"><span data-stu-id="1fd31-176">Configure Active Directory Federation Services (AD FS 2.0)</span></span>

<span data-ttu-id="1fd31-177">Cette section décrit la configuration d’Active Directory Federation Services (AD FS 2.0) pour prendre en charge l’authentification multifacteur.</span><span class="sxs-lookup"><span data-stu-id="1fd31-177">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="1fd31-178">Pour plus d’informations sur l’installation de la 2,0 AD FS, voir [instructions pas à pas sur AD fs 2,0 et guide](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span><span class="sxs-lookup"><span data-stu-id="1fd31-178">For information on how to install AD FS 2.0, see [AD FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374).</span></span>

> [!NOTE]
> <span data-ttu-id="1fd31-179">Lorsque vous installez AD FS 2.0, vous ne devez pas utiliser le Gestionnaire de serveur Windows pour ajouter le rôle Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="1fd31-179">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="1fd31-180">Au lieu de cela, téléchargez et installez le [package 2,0 de services ADFS (Active Directory Federation Services](https://go.microsoft.com/fwlink/p/?LinkId=313375)).</span><span class="sxs-lookup"><span data-stu-id="1fd31-180">Instead, download and install the [Active Directory Federation Services 2.0 RTW package](https://go.microsoft.com/fwlink/p/?LinkId=313375).</span></span>

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a><span data-ttu-id="1fd31-181">Pour configurer AD FS pour l’authentification à deux facteurs</span><span class="sxs-lookup"><span data-stu-id="1fd31-181">To configure AD FS for two-factor Authentication</span></span>

1. <span data-ttu-id="1fd31-182">Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="1fd31-182">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="1fd31-183">Lancez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fd31-183">Start Windows PowerShell.</span></span>

3. <span data-ttu-id="1fd31-184">À partir de la ligne de commande Windows PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-184">From the Windows PowerShell command-line, run the following command:</span></span>

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. <span data-ttu-id="1fd31-185">Établissez un partenariat avec chaque serveur pour lequel l’authentification passive sera activée, en exécutant la commande ci-dessous, en remplaçant le nom du serveur propre à votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="1fd31-185">Establish a partnership with each server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. <span data-ttu-id="1fd31-186">Dans le menu Outils d’administration, lancez la console de gestion AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1fd31-186">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6. <span data-ttu-id="1fd31-187">Développez **relations d’approbation** > de confiance entre les**parties**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-187">Expand **Trust Relationships** > **Relying Party Trusts**.</span></span>

7. <span data-ttu-id="1fd31-188">Vérifiez qu’une nouvelle approbation a été créée pour votre serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1fd31-188">Verify that a new trust has been created for your Skype for Business Server.</span></span>

8. <span data-ttu-id="1fd31-189">Créez et affectez une règle d’autorisation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fd31-189">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. <span data-ttu-id="1fd31-190">Créez et affectez une règle de transformation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1fd31-190">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. <span data-ttu-id="1fd31-191">Dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur votre relation d’approbation de la partie de confiance, puis sélectionnez **Modifier les règles de revendication**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-191">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="1fd31-192">Sélectionnez l’onglet **Règles d’autorisation d’émission**, puis vérifiez que la règle d’autorisation a été correctement créée.</span><span class="sxs-lookup"><span data-stu-id="1fd31-192">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="1fd31-193">Sélectionnez l’onglet **Règles de transformation d’émission**, puis vérifiez que la règle de transformation d’émission a été créée correctement.</span><span class="sxs-lookup"><span data-stu-id="1fd31-193">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="1fd31-194">Configuration d’AD FS 2.0 pour prendre en charge l’authentification du client</span><span class="sxs-lookup"><span data-stu-id="1fd31-194">Configuring AD FS 2.0 to support client authentication</span></span>

<span data-ttu-id="1fd31-195">Deux types d’authentifications peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :</span><span class="sxs-lookup"><span data-stu-id="1fd31-195">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

- <span data-ttu-id="1fd31-196">Authentification basée sur les formulaires</span><span class="sxs-lookup"><span data-stu-id="1fd31-196">Forms-based authentication (FBA)</span></span>

- <span data-ttu-id="1fd31-197">Authentification de client TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="1fd31-197">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="1fd31-198">L’authentification basée sur les formulaires permet de développer une page web permettant aux utilisateurs de s’authentifier à l’aide de leur nom d’utilisateur et de leur mot de passe ou de leur carte à puce et de leur code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="1fd31-198">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="1fd31-199">Cette rubrique décrit la mise en œuvre de l’authentification de client TLS (Transport Layer Security) avec AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="1fd31-199">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="1fd31-200">Pour plus d’informations sur les types d’authentifications 2,0 d’AD FS, voir [ad fs 2,0: Comment changer le type d’authentification locale](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span><span class="sxs-lookup"><span data-stu-id="1fd31-200">For more information about AD FS 2.0 authentication types, see [AD FS 2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).</span></span>

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a><span data-ttu-id="1fd31-201">Pour configurer AD FS 2.0 pour prendre en charge l’authentification du client</span><span class="sxs-lookup"><span data-stu-id="1fd31-201">To Configure AD FS 2.0 to Support Client Authentication</span></span>

1. <span data-ttu-id="1fd31-202">Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="1fd31-202">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2. <span data-ttu-id="1fd31-203">Lancez l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="1fd31-203">Launch Windows Explorer.</span></span>

3. <span data-ttu-id="1fd31-204">Accédez à C:\inetpub\adfs\ls.</span><span class="sxs-lookup"><span data-stu-id="1fd31-204">Browse to C:\inetpub\adfs\ls</span></span>

4. <span data-ttu-id="1fd31-205">Effectuez une copie de sauvegarde du fichier web.config existant.</span><span class="sxs-lookup"><span data-stu-id="1fd31-205">Make a backup copy of the existing web.config file.</span></span>

5. <span data-ttu-id="1fd31-206">Ouvrez le fichier web.config existant à l’aide du Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="1fd31-206">Open the existing web.config file using Notepad.</span></span>

6. <span data-ttu-id="1fd31-207">Dans la barre de menus, sélectionnez **Edition**, puis **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-207">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7. <span data-ttu-id="1fd31-208">Recherchez \<localAuthenticationTypes\>.</span><span class="sxs-lookup"><span data-stu-id="1fd31-208">Search for \<localAuthenticationTypes\>.</span></span>

    <span data-ttu-id="1fd31-209">Quatre types d’authentification s’affichent (un par ligne).</span><span class="sxs-lookup"><span data-stu-id="1fd31-209">Note that there are four authentication types listed, one per line.</span></span>

8. <span data-ttu-id="1fd31-210">Déplacez la ligne contenant le type d’authentification TLSClient au début de la liste dans la section.</span><span class="sxs-lookup"><span data-stu-id="1fd31-210">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9. <span data-ttu-id="1fd31-211">Enregistrez et fermez le fichier web.config.</span><span class="sxs-lookup"><span data-stu-id="1fd31-211">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="1fd31-212">Lancez une invite de commandes avec des droits élevés.</span><span class="sxs-lookup"><span data-stu-id="1fd31-212">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="1fd31-213">Redémarrez IIS en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-213">Restart IIS by running the following command:</span></span>

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a><span data-ttu-id="1fd31-214">Configuration de l’authentification passive Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1fd31-214">Configuring Skype for Business Server passive authentication</span></span>

<span data-ttu-id="1fd31-215">La section suivante décrit comment configurer Skype entreprise Server pour prendre en charge l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="1fd31-215">The following section describes how to configure Skype for Business Server to support passive authentication.</span></span> <span data-ttu-id="1fd31-216">Dès qu’il est activé, les utilisateurs dotés de l’authentification à deux facteurs doivent utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide du client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1fd31-216">Once enabled, users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="1fd31-p109">Il est vivement recommandé que les clients activent l’authentification passive pour les services Serveur d’inscriptions et web au niveau du service. L’activation au niveau global risquerait de provoquer des échecs d’authentification à l’échelle de l’organisation pour les utilisateurs qui ne se connectent pas avec le client de bureau pris en charge.</span><span class="sxs-lookup"><span data-stu-id="1fd31-p109">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level. If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the supported desktop client.</span></span>

### <a name="web-service-configuration"></a><span data-ttu-id="1fd31-219">Configuration des services web</span><span class="sxs-lookup"><span data-stu-id="1fd31-219">Web Service Configuration</span></span>

<span data-ttu-id="1fd31-220">La procédure ci-dessous décrit la création d’une configuration de service web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.</span><span class="sxs-lookup"><span data-stu-id="1fd31-220">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-web-service-configuration"></a><span data-ttu-id="1fd31-221">Pour créer une configuration de service web personnalisée</span><span class="sxs-lookup"><span data-stu-id="1fd31-221">To create a custom web service configuration</span></span>

1. <span data-ttu-id="1fd31-222">Connectez-vous à votre serveur frontal Skype entreprise Server à l’aide d’un compte d’administrateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1fd31-222">Log in to your Skype for Business Server Front End server using a Skype for Business administrator account.</span></span>

2. <span data-ttu-id="1fd31-223">Lancez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1fd31-223">Launch the Skype for Business Server Management Shell.</span></span>

3. <span data-ttu-id="1fd31-224">À partir de la ligne de commande de Skype entreprise Server Management Shell, créez une nouvelle configuration de service Web pour chaque directeur, pool d’entreprise et serveur Standard Edition qui sera activé pour l’authentification passive en exécutant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="1fd31-224">From the Skype for Business Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > <span data-ttu-id="1fd31-p110">La valeur du nom de domaine complet WsFedPassiveMetadataUri correspond au nom du service de fédération de votre serveur AD FS 2.0. Pour consulter la valeur Nom du service de fédération dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur **Service** dans le volet de navigation, puis sélectionnez **Modifier les propriétés du service de fédération**.</span><span class="sxs-lookup"><span data-stu-id="1fd31-p110">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on **Service** from the navigation pane and then selecting **Edit Federation Service Properties**.</span></span>

4. <span data-ttu-id="1fd31-227">Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été définies correctement en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-227">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. <span data-ttu-id="1fd31-228">Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification de ticket web.</span><span class="sxs-lookup"><span data-stu-id="1fd31-228">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="1fd31-229">Pour tous les directeurs, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans Skype entreprise Web services en exécutant l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="1fd31-229">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Skype for Business Web Services by running the following cmdlet:</span></span>

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. <span data-ttu-id="1fd31-230">Vérifiez que tous les autres types d’authentification ont été désactivés correctement en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-230">Verify that all other authentication types have been successfully disabled by running the following cmdlet:</span></span>

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a><span data-ttu-id="1fd31-231">Configuration du serveur proxy</span><span class="sxs-lookup"><span data-stu-id="1fd31-231">Proxy Configuration</span></span>

<span data-ttu-id="1fd31-232">Lorsque l’authentification par certificat est désactivée pour les services Web Skype entreprise, le client Skype entreprise utilise un type d’authentification moins favori, tel que Kerberos ou NTLM, pour s’authentifier auprès du service d’inscription.</span><span class="sxs-lookup"><span data-stu-id="1fd31-232">When certificate authentication is disabled for Skype for Business Web Services, the Skype for Business client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="1fd31-233">Si l’authentification par certificat est toujours requise pour autoriser le client à extraire un ticket web, Kerberos et NTLM doivent tout de même être désactivés pour le service Serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="1fd31-233">Certificate authentication is still needed to allow the client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="1fd31-234">La procédure ci-dessous décrit la création d’une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.</span><span class="sxs-lookup"><span data-stu-id="1fd31-234">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

### <a name="to-create-a-custom-proxy-configuration"></a><span data-ttu-id="1fd31-235">Pour créer une configuration de proxy personnalisée</span><span class="sxs-lookup"><span data-stu-id="1fd31-235">To create a custom proxy configuration</span></span>

1. <span data-ttu-id="1fd31-236">À partir de la ligne de commande de l’interpréteur de commandes de Skype entreprise Server Management Shell, créez une nouvelle configuration de proxy pour chaque pool de périphériques de type «pool d’entreprise» et serveur standard pour l’authentification passive en exécutant ce qui suit: disponibles</span><span class="sxs-lookup"><span data-stu-id="1fd31-236">From the Skype for Business Server Management Shell command-line, create a new proxy configuration for each Skype for Business Server Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. <span data-ttu-id="1fd31-237">Vérifiez que tous les autres types d’authentification proxy ont été désactivés correctement en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1fd31-237">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a><span data-ttu-id="1fd31-238">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fd31-238">See also</span></span>

[<span data-ttu-id="1fd31-239">Gestion de l’authentification à deux facteurs dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1fd31-239">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)

[<span data-ttu-id="1fd31-240">Utiliser l’authentification à deux facteurs avec le client Skype entreprise et Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1fd31-240">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>](use-two-factor.md)
