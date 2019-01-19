---
title: Configurer l’intégration Cloud Connector avec votre client Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Découvrez comment configurer l’intégration de nuage connecteur avec votre client Office 365.
ms.openlocfilehash: 837775fea5a128dbbb8d143f15064e08d9267756
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729378"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="84a4b-103">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="84a4b-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="84a4b-104">Découvrez comment configurer l’intégration de nuage connecteur avec votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="84a4b-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="84a4b-105">Une fois l’installation de Skype Entreprise, version Cloud Connector achevée, les étapes décrites dans cette rubrique vous permettront de configurer votre déploiement et de le connecter à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="84a4b-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="84a4b-106">Configurer les paramètres du pare-feu</span><span class="sxs-lookup"><span data-stu-id="84a4b-106">Configure firewall settings</span></span>

<span data-ttu-id="84a4b-107">Configurer les paramètres de pare-feu pour les paramètres de pare-feu internes et externes de votre réseau de périmètre ouvrir les ports requis, comme décrit dans les [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) dans [planifier Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="84a4b-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="84a4b-108">Configuration de passerelles PSTN (réseau téléphonique commuté)</span><span class="sxs-lookup"><span data-stu-id="84a4b-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="84a4b-p101">Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.</span><span class="sxs-lookup"><span data-stu-id="84a4b-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="84a4b-112">Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :</span><span class="sxs-lookup"><span data-stu-id="84a4b-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="84a4b-113">Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="84a4b-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="84a4b-114">Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="84a4b-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="84a4b-p102">Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :</span><span class="sxs-lookup"><span data-stu-id="84a4b-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="84a4b-117">Modifier le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés d’inscrire ou créer un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="84a4b-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="84a4b-118">Pour obtenir des instructions détaillées, reportez-vous à la page [Modèles de certificats](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="84a4b-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="84a4b-119">Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé.</span><span class="sxs-lookup"><span data-stu-id="84a4b-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="84a4b-120">Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé.</span><span class="sxs-lookup"><span data-stu-id="84a4b-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="84a4b-121">Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.</span><span class="sxs-lookup"><span data-stu-id="84a4b-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="84a4b-122">Mettez à jour le domaine pour votre client</span><span class="sxs-lookup"><span data-stu-id="84a4b-122">Update the domain for your tenant</span></span>

<span data-ttu-id="84a4b-123">Assurez-vous d’avoir accompli les étapes pour mettre à jour votre domaine dans Office 365 et d’avoir la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="84a4b-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="84a4b-124">Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, voir [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="84a4b-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="84a4b-125">Ajouter des enregistrements dans Office 365 pour Edge</span><span class="sxs-lookup"><span data-stu-id="84a4b-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="84a4b-126">Ajoutez les enregistrements DNS suivants à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="84a4b-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="84a4b-127">Pour obtenir des informations sur l'ajout d'enregistrements DNS à votre client Office 365, consultez [Ajouter ou modifier des enregistrements DNS personnalisés dans Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="84a4b-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="84a4b-128">Ajouter un enregistrement DNS A pour le serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="84a4b-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="84a4b-p107">Les enregistrements SRV seront automatiquement créés par Office 365 et les scripts de déploiement. Vérifiez que vous pouvez voir les deux services SIP suivants sur Edge : _sip et _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="84a4b-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="84a4b-132">Configurationd’une connectivité hybride entre la version Cloud Connector et Office 365</span><span class="sxs-lookup"><span data-stu-id="84a4b-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="84a4b-133">Pour configurer la connectivité hybride entre votre Skype pour le déploiement dans le nuage connecteur Édition et votre client Office 365, exécutez l’applet de commande suivante dans une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="84a4b-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="84a4b-134">Pour savoir comment établir une session PowerShell distante, consultez : [configuration de votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="84a4b-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="84a4b-135">L’applet de commande définit le nom de domaine complet du serveur dʼaccès Edge.</span><span class="sxs-lookup"><span data-stu-id="84a4b-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="84a4b-136">Dans la première des commandes, le \<externe Access Edge FQDN\> doit être l’un pour le rôle de serveur Edge d’accès SIP.</span><span class="sxs-lookup"><span data-stu-id="84a4b-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="84a4b-137">Par défaut, il doit s’agir ap.\<nom de domaine\>.</span><span class="sxs-lookup"><span data-stu-id="84a4b-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="84a4b-138">Externe Access Edge nom de domaine complet utilisé pour la Destination de l’homologue doit être défini à un site PSTN qui sera uniquement utilisé comme un secours au cas où un utilisateur n’est pas affecté à un site PSTN.</span><span class="sxs-lookup"><span data-stu-id="84a4b-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="84a4b-139">Pour plus d’informations, reportez-vous à la rubrique [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="84a4b-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="84a4b-140">Configurer les passerelles RTC</span><span class="sxs-lookup"><span data-stu-id="84a4b-140">Set up PSTN gateways</span></span>

<span data-ttu-id="84a4b-p111">Configurez les jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.</span><span class="sxs-lookup"><span data-stu-id="84a4b-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="84a4b-144">Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :</span><span class="sxs-lookup"><span data-stu-id="84a4b-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="84a4b-145">Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="84a4b-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="84a4b-146">Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="84a4b-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="84a4b-p112">Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :</span><span class="sxs-lookup"><span data-stu-id="84a4b-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="84a4b-149">Modifiez le modèle Serveur web existant pour permettre aux utilisateurs authentifiés de s’inscrire ou de créer un modèle Serveur web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="84a4b-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="84a4b-150">Pour obtenir des instructions détaillées, reportez-vous à la page [Modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="84a4b-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="84a4b-151">Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé.</span><span class="sxs-lookup"><span data-stu-id="84a4b-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="84a4b-152">Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé.</span><span class="sxs-lookup"><span data-stu-id="84a4b-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="84a4b-153">Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.</span><span class="sxs-lookup"><span data-stu-id="84a4b-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="84a4b-154">La ou les passerelle(s) RTC d’un site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site.</span><span class="sxs-lookup"><span data-stu-id="84a4b-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="84a4b-155">Configurez vos utilisateurs dans Office 365</span><span class="sxs-lookup"><span data-stu-id="84a4b-155">Set up your users in Office 365</span></span>

<span data-ttu-id="84a4b-156">Ouvrez une session le portail d’administration d’Office 365, ajoutez les utilisateurs qui seront activés pour les services en ligne, puis d’affecter une licence E5 ou un système téléphonique dans Office 365 module complémentaire à la licence E3 à ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="84a4b-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="84a4b-157">Pour plus d’informations sur l’ajout d’utilisateurs, voir [Ajouter des utilisateurs à Office 365 pour entreprises](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="84a4b-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="84a4b-158">Permettre aux utilisateurs pour le système téléphonique dans les services voix et de la messagerie vocale d’Office 365</span><span class="sxs-lookup"><span data-stu-id="84a4b-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="84a4b-159">Après avoir ajouté vos utilisateurs vers Office 365, activer leur compte de système téléphonique dans les services de téléphonie Office 365, y compris la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="84a4b-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="84a4b-160">Pour activer ces fonctionnalités, vous devez vous connecter à votre client Office 365 avec un compte de rôle d’administrateur général Office 365, et être en mesure d’exécuter PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="84a4b-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="84a4b-161">Pour savoir comment établir une session PowerShell distante, consultez : [configuration de votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="84a4b-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="84a4b-162">Attribuer la stratégie à l’utilisateur et configurez vocale numéro de téléphone professionnel l’utilisateur, que vous pouvez spécifier avec la valeur du paramètre **Identity** :</span><span class="sxs-lookup"><span data-stu-id="84a4b-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="84a4b-163">Vous pouvez également spécifier l’identité d’un utilisateur par son adresse SIP, son nom d’utilisateur principal (UPN), son nom de domaine et nom d’utilisateur (domaine\nom d’utilisateur) et le nom d’affichage dans Active Directory (« Bob Kelly »). </span><span class="sxs-lookup"><span data-stu-id="84a4b-163">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="84a4b-164">Vous pouvez vérifier que les utilisateurs ont été ajoutés et activés à l’aide du script suivant :</span><span class="sxs-lookup"><span data-stu-id="84a4b-164">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="84a4b-p117">Vous devrez décider si vos utilisateurs peuvent passer des appels internationaux. Par défaut, les appels internationaux sont activés. Vous pouvez désactiver ou activer la numérotation internationale pour des utilisateurs à l’aide du centre d’administration Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="84a4b-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="84a4b-168">Pour désactiver la numération internationale pour des utilisateurs spécifiques, exécutez l’applet de commande suivante dans le module Skype Entreprise Online pour PowerShell :</span><span class="sxs-lookup"><span data-stu-id="84a4b-168">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="84a4b-169">Pour réactiver international l’appel sur chaque utilisateur une fois qu’il a été désactivé, exécutez l’applet de commande même, mais remplacez la valeur de **PolicyName** *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="84a4b-169">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="84a4b-170">Affecter les utilisateurs aux sites RTC</span><span class="sxs-lookup"><span data-stu-id="84a4b-170">Assign users to PSTN sites</span></span>

<span data-ttu-id="84a4b-171">Utilisez PowerShell en client distant pour affecter un site aux utilisateurs, même si vous avez déployé un site unique.</span><span class="sxs-lookup"><span data-stu-id="84a4b-171">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="84a4b-172">Pour savoir comment établir une session PowerShell distante, consultez : [configuration de votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="84a4b-172">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="84a4b-173">Si aucun site RTC n’est affecté à un utilisateur, la connectivité hybride entre votre déploiement de la version Cloud Connector de Skype Entreprise et votre client Office 365 utilisera celui par défaut au niveau de client (destination des pairs) pour pouvoir achever les appels.</span><span class="sxs-lookup"><span data-stu-id="84a4b-173">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="84a4b-174">Configuration des paramètres du serveur de médiation hybride en ligne</span><span class="sxs-lookup"><span data-stu-id="84a4b-174">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="84a4b-175"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="84a4b-175"></span></span>

<span data-ttu-id="84a4b-176">Lorsqu’un appel P2P est transmis à une conférence PSTN, le Skype pour le serveur de conférence en ligne Business envoie une invitation au serveur de médiation de connecteur dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="84a4b-176">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="84a4b-177">Pour vous assurer qu’Office 365 peut acheminer cette invitation avec succès, vous devez configurer un paramètre de votre client en ligne pour chaque serveur de médiation dans le nuage connecteur comme suit :</span><span class="sxs-lookup"><span data-stu-id="84a4b-177">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="84a4b-178">Créer un utilisateur dans le portail d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="84a4b-178">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="84a4b-179">Utilisez n’importe quel nom d’utilisateur, tel que « MediationServer1 ».</span><span class="sxs-lookup"><span data-stu-id="84a4b-179">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="84a4b-180">Utilisez le domaine SIP par défaut du nuage connecteur (le premier domaine SIP dans le fichier .ini) en tant que le domaine de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84a4b-180">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="84a4b-181">Veuillez noter qu’affectation de licence n’est requis pour la propagation de l’utilisateur dans le Skype pour annuaire d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="84a4b-181">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="84a4b-182">Affecter un Office 365 sous licence (par exemple, E5) pour le compte que vous créez, autoriser une heure pour que les modifications à propager, vérifiez les comptes d’utilisateur a été configuré correctement pour la Skype pour annuaire d’entreprise en ligne par l’applet de commande suivante en cours d’exécution, puis supprimez le licence de ce compte.</span><span class="sxs-lookup"><span data-stu-id="84a4b-182">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```
   Gets-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="84a4b-183">Démarrer une session PowerShell distante client Azure AD à l’aide de vos paramètres globaux ou les informations d’identification d’administration, puis exécutez l’applet de commande suivante pour définir le service pour le compte d’utilisateur AD Azure configuré dans l’étape 1 à « HybridMediationServer » :</span><span class="sxs-lookup"><span data-stu-id="84a4b-183">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="84a4b-184">Démarrez un client Skype pour session PowerShell distante métiers à l’aide de votre Skype pour les informations d’identification d’administration de Business client et puis exécutez l’applet de commande suivante pour définir le serveur de médiation et le FQDN du serveur Edge à cet utilisateur de compte, remplaçant \<DisplayName\> avec le nom complet de l’utilisateur pour le compte que vous avez créé à l’étape 1 :</span><span class="sxs-lookup"><span data-stu-id="84a4b-184">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="84a4b-185">Pour l’identité, utilisez le nom d’affichage du compte utilisateur Office 365 que vous avez créé pour ce serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="84a4b-185">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="84a4b-186">Pour *MediationServerFQDN* , utilisez le nom de domaine complet interne définie pour votre serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="84a4b-186">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="84a4b-187">Pour *EdgeServerExternalFQDN* , utilisez le nom de domaine complet externe définie pour le Proxy d’accès serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="84a4b-187">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="84a4b-188">Si plusieurs sites RTC Cloud Connector existent, choisissez le FQDN du proxy du serveur Edge d’accès affecté au site qui contient la localisation du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="84a4b-188">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="84a4b-189">Si plusieurs serveurs de médiation Cloud Connector existent (plusieurs sites en haute disponibilité), veuillez répéter les étapes précédentes pour chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="84a4b-189">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

