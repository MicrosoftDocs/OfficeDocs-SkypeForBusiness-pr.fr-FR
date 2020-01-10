---
title: Configurer l’intégration Cloud Connector avec votre client Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Apprenez à configurer l’intégration du connecteur Cloud à votre client Office 365.
ms.openlocfilehash: ed9437026ddbae07aadbe81585886ed0cb5cb0cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002854"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="71f03-103">Configure Cloud Connector integration with your Office 365 tenant</span><span class="sxs-lookup"><span data-stu-id="71f03-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="71f03-104">Apprenez à configurer l’intégration du connecteur Cloud à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="71f03-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="71f03-105">Une fois l’installation de Skype Entreprise, version Cloud Connector achevée, les étapes décrites dans cette rubrique vous permettront de configurer votre déploiement et de le connecter à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="71f03-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="71f03-106">Configurer les paramètres du pare-feu</span><span class="sxs-lookup"><span data-stu-id="71f03-106">Configure firewall settings</span></span>

<span data-ttu-id="71f03-107">Configurez les paramètres de pare-feu pour votre réseau de périmètre pour l’ouverture des ports requis, comme décrit dans la rubrique [ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) du [plan de Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="71f03-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="71f03-108">Configuration de passerelles PSTN (réseau téléphonique commuté)</span><span class="sxs-lookup"><span data-stu-id="71f03-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="71f03-p101">Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.</span><span class="sxs-lookup"><span data-stu-id="71f03-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="71f03-112">Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :</span><span class="sxs-lookup"><span data-stu-id="71f03-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="71f03-113">Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="71f03-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="71f03-114">Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="71f03-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="71f03-p102">Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :</span><span class="sxs-lookup"><span data-stu-id="71f03-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="71f03-117">Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="71f03-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="71f03-118">Pour obtenir des instructions détaillées, voir [modèles de certificats](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="71f03-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="71f03-119">Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé.</span><span class="sxs-lookup"><span data-stu-id="71f03-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="71f03-120">Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé.</span><span class="sxs-lookup"><span data-stu-id="71f03-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="71f03-121">Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.</span><span class="sxs-lookup"><span data-stu-id="71f03-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="71f03-122">Mettez à jour le domaine pour votre client</span><span class="sxs-lookup"><span data-stu-id="71f03-122">Update the domain for your tenant</span></span>

<span data-ttu-id="71f03-123">Assurez-vous d’avoir accompli les étapes pour mettre à jour votre domaine dans Office 365 et d’avoir la possibilité d’ajouter des enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="71f03-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="71f03-124">Pour plus d’informations sur la configuration de votre domaine dans Office 365, voir [Ajouter un domaine à office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="71f03-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="71f03-125">Ajouter des enregistrements dans Office 365 pour Edge</span><span class="sxs-lookup"><span data-stu-id="71f03-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="71f03-126">Ajoutez les enregistrements DNS suivants à votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="71f03-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="71f03-127">Pour plus d’informations sur l’ajout d’enregistrements DNS à votre client 365 Office, voir [Ajouter ou modifier des enregistrements DNS personnalisés dans Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="71f03-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="71f03-128">Ajouter un enregistrement DNS A pour le serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="71f03-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="71f03-p107">Les enregistrements SRV seront automatiquement créés par Office 365 et les scripts de déploiement. Vérifiez que vous pouvez voir les deux services SIP suivants sur Edge : _sip et _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="71f03-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="71f03-132">Configurationd’une connectivité hybride entre la version Cloud Connector et Office 365</span><span class="sxs-lookup"><span data-stu-id="71f03-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="71f03-133">Pour configurer une connectivité hybride entre le déploiement de Skype entreprise version Cloud Connector et votre client Office 365, exécutez l’applet de commande suivante dans une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="71f03-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="71f03-134">Pour plus d’informations sur l’établissement d’une session PowerShell distante, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="71f03-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="71f03-135">L’applet de commande définit le FQDN externe du serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="71f03-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="71f03-136">Dans la première des commandes, le \<nom de domaine complet\> du périmètre d’accès externe doit être celui du rôle de périmètre d’accès SIP.</span><span class="sxs-lookup"><span data-stu-id="71f03-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="71f03-137">Par défaut, il doit s’agir du\<nom\>d’accès du domaine.</span><span class="sxs-lookup"><span data-stu-id="71f03-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="71f03-138">Le nom de domaine complet du périmètre d’accès externe utilisé pour la destination homologue doit être défini sur un site PSTN qui sera utilisé uniquement comme secours au cas où un utilisateur n’est pas attribué à un site PSTN.</span><span class="sxs-lookup"><span data-stu-id="71f03-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="71f03-139">Pour plus d’informations, reportez-vous à la rubrique [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="71f03-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="71f03-140">Configurer les passerelles RTC</span><span class="sxs-lookup"><span data-stu-id="71f03-140">Set up PSTN gateways</span></span>

<span data-ttu-id="71f03-p111">Configurez les jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.</span><span class="sxs-lookup"><span data-stu-id="71f03-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="71f03-144">Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :</span><span class="sxs-lookup"><span data-stu-id="71f03-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="71f03-145">Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="71f03-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="71f03-146">Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="71f03-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="71f03-p112">Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :</span><span class="sxs-lookup"><span data-stu-id="71f03-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="71f03-149">Modifiez le modèle du serveur Web existant pour autoriser les utilisateurs authentifiés à s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et autoriser les utilisateurs authentifiés à s’inscrire.</span><span class="sxs-lookup"><span data-stu-id="71f03-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="71f03-150">Pour obtenir des instructions détaillées, voir [modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="71f03-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="71f03-151">Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé.</span><span class="sxs-lookup"><span data-stu-id="71f03-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="71f03-152">Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé.</span><span class="sxs-lookup"><span data-stu-id="71f03-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="71f03-153">Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.</span><span class="sxs-lookup"><span data-stu-id="71f03-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="71f03-154">La ou les passerelle(s) RTC d’un site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site.</span><span class="sxs-lookup"><span data-stu-id="71f03-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="71f03-155">Configurez vos utilisateurs dans Office 365</span><span class="sxs-lookup"><span data-stu-id="71f03-155">Set up your users in Office 365</span></span>

<span data-ttu-id="71f03-156">Connectez-vous au portail d’administration Office 365, ajoutez les utilisateurs qui seront activés pour les services vocaux en ligne et attribuez une licence ou un système téléphonique E5 dans le module complémentaire Office 365 à la licence E3 pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="71f03-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="71f03-157">Pour plus d’informations sur l’ajout d’utilisateurs, voir [Ajouter des utilisateurs à Office 365 pour les entreprises](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="71f03-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="71f03-158">Permettre aux utilisateurs de système téléphonique dans Office 365 des services vocaux et de messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="71f03-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="71f03-159">Après avoir ajouté vos utilisateurs à Office 365, activez leurs comptes pour le système téléphonique dans les services vocaux d’Office 365, y compris la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="71f03-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="71f03-160">Pour activer ces fonctionnalités, vous devez vous connecter à votre client Office 365 avec un compte de rôle d’administrateur général Office 365, et être en mesure d’exécuter PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="71f03-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="71f03-161">Pour plus d’informations sur l’établissement d’une session PowerShell distante, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="71f03-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="71f03-162">Affectez la stratégie à votre utilisateur et configurez le numéro de téléphone professionnel de l’utilisateur, que vous spécifiez avec la valeur du paramètre **Identity** :</span><span class="sxs-lookup"><span data-stu-id="71f03-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="71f03-163">Vous pouvez spécifier une identité d’utilisateur à l’aide de l’adresse SIP de l’utilisateur, du nom d’utilisateur principal (UPN) ou du nom complet de l’utilisateur Active Directory (par exemple, « Robert Kelly »).</span><span class="sxs-lookup"><span data-stu-id="71f03-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="71f03-164">Le caractère astérisque\*() peut également être utilisé avec le nom complet comme identité d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="71f03-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="71f03-165">Par exemple, l’identité «\*Smith » renvoie tous les utilisateurs dont le nom d’affichage se termine par la valeur de chaîne « Dupont ».</span><span class="sxs-lookup"><span data-stu-id="71f03-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="71f03-166">Vous pouvez ensuite vérifier que les utilisateurs ont été ajoutés et activés grâce au script suivant :</span><span class="sxs-lookup"><span data-stu-id="71f03-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="71f03-p118">Vous devrez décider d'autoriser ou non les utilisateurs à passer des appels internationaux. Par défaut, les appels internationaux sont activés. Vous pouvez activer ou désactiver les appels internationaux pour des utilisateurs grâce au centre d’administration Skype Entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="71f03-p118">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="71f03-170">Pour désactiver les appels internationaux au niveau de l’utilisateur, exécutez l’applet de commande suivante dans PowerShell de Skype Entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="71f03-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="71f03-171">Pour réactiver les appels internationaux en fonction de la manière dont elle a été désactivée, exécutez la même applet de la même façon, mais remplacez la valeur de **PolicyName** par *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="71f03-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="71f03-172">Affecter les utilisateurs aux sites RTC</span><span class="sxs-lookup"><span data-stu-id="71f03-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="71f03-173">Utilisez PowerShell en client distant pour affecter un site aux utilisateurs, même si vous avez déployé un site unique.</span><span class="sxs-lookup"><span data-stu-id="71f03-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="71f03-174">Pour plus d’informations sur l’établissement d’une session PowerShell distante, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="71f03-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="71f03-175">Si aucun site RTC n’est affecté à un utilisateur, la connectivité hybride entre votre déploiement de la version Cloud Connector de Skype Entreprise et votre client Office 365 utilisera celui par défaut au niveau de client (destination des pairs) pour pouvoir achever les appels.</span><span class="sxs-lookup"><span data-stu-id="71f03-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="71f03-176">Configuration des paramètres du serveur de médiation hybride en ligne</span><span class="sxs-lookup"><span data-stu-id="71f03-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="71f03-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="71f03-177"></span></span>

<span data-ttu-id="71f03-178">Lorsqu’un appel P2P est transféré vers une conférence RTC, le serveur de conférence Skype entreprise Online envoie une invitation au serveur de médiation Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="71f03-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="71f03-179">Pour vous assurer qu’Office 365 peut diriger cette invitation, vous devez configurer un paramètre dans votre client en ligne pour chaque serveur de médiation du Cloud Cloud comme suit :</span><span class="sxs-lookup"><span data-stu-id="71f03-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="71f03-180">Créer un utilisateur dans le portail d’administration 365 Office.</span><span class="sxs-lookup"><span data-stu-id="71f03-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="71f03-181">Utilisez le nom d’utilisateur de votre choix (par exemple, « MediationServer1 »).</span><span class="sxs-lookup"><span data-stu-id="71f03-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="71f03-182">Utilisez le domaine SIP par défaut de Cloud Connector (le premier domaine SIP du fichier. ini) en tant que domaine de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="71f03-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="71f03-183">Veuillez noter que l’attribution de licence est uniquement requise pour la propagation de l’utilisateur dans l’annuaire Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="71f03-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="71f03-184">Attribution d’une licence Office 365 (par exemple, E5) au compte que vous créez, autorisant jusqu’à une heure pour que les modifications soient propagées, vérifiez que les comptes d’utilisateurs ont été correctement configurés pour le répertoire Skype entreprise Online en exécutant l’applet de commande suivante, puis supprimez le licence de ce compte.</span><span class="sxs-lookup"><span data-stu-id="71f03-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="71f03-185">Démarrez une session de connexion distante Azure AD à un client à l’aide de vos informations d’identification d’administrateur général ou d’utilisateur, puis exécutez l’applet de commande suivante pour définir le service pour le compte d’utilisateur Azure AD configuré à l’étape 1 sur « HybridMediationServer » :</span><span class="sxs-lookup"><span data-stu-id="71f03-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="71f03-186">Démarrez une session PowerShell distante Skype entreprise à l’aide de vos informations d’identification d’administrateur de clients Skype entreprise, puis exécutez l’applet de commande suivante pour définir le nom de domaine complet du serveur \<de\> médiation et du client Edge pour ce compte d’utilisateur, en remplaçant DisplayName par le nom complet de l’utilisateur pour le compte que vous avez créé à l’étape 1 :</span><span class="sxs-lookup"><span data-stu-id="71f03-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="71f03-187">Pour l’identité, utilisez le nom d’affichage du compte utilisateur Office 365 que vous avez créé pour ce serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="71f03-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="71f03-188">Pour *MediationServerFQDN* , utilisez le FQDN interne défini pour votre serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="71f03-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="71f03-189">Pour *EdgeServerExternalFQDN* , utilisez le FQDN externe défini pour le proxy d’accès Edge Server.</span><span class="sxs-lookup"><span data-stu-id="71f03-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="71f03-190">Si plusieurs sites RTC Cloud Connector existent, choisissez le FQDN du proxy du serveur Edge d’accès affecté au site qui contient la localisation du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="71f03-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="71f03-191">Si plusieurs serveurs de médiation Cloud Connector existent (plusieurs sites en haute disponibilité), veuillez répéter les étapes précédentes pour chacun d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="71f03-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

