---
title: Configurer l’intégration de Cloud Connector avec Microsoft 365 ou Office 365 organisation
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Découvrez comment configurer l’intégration de Cloud Connector avec Microsoft 365 ou Office 365 organisation.
ms.openlocfilehash: b3b8b13669a2e52ed5146e1bd0ca179a5542e43d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733373"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurer l’intégration de Cloud Connector avec Microsoft 365 ou Office 365 organisation

> [!Important] 
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Découvrez comment configurer l’intégration de Cloud Connector avec Microsoft 365 ou Office 365 organisation.
  
Une fois Skype Entreprise Cloud Connector Edition’installation, effectuez les étapes de cette section pour configurer votre déploiement et le connecter à Microsoft 365 ou Office 365 organisation.
  
## <a name="configure-firewall-settings"></a>Configurer les paramètres de pare-feu

Configurez les paramètres de pare-feu pour vos paramètres de pare-feu interne et externe pour que votre réseau de périmètre ouvre les ports requis, comme décrit dans Ports et [protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) dans [Plan for Skype Entreprise Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurer des passerelles de réseau téléphonique commuté (PSTN)

Configurer des trunks sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation pour toutes les appliances. Étant donné que le nom de pool est le même pour tous les serveurs du pool, chaque trunk doit pointer vers un nom de groupe ou une adresse IP du serveur de médiation au lieu du nom de pool de serveurs de médiation. Les trunks doivent être définies dans la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devez configurer les passerelles et les serveurs de médiation pour prendre en charge MTLS comme suit :
  
1. Exporte l’autorité de contrôle d’autorité de contrôle racine à partir de l’ordinateur Active Directory cloud Connector.
    
2. Suivez les instructions du fournisseur de passerelle PSTN pour importer l’ac racine.
    
3. Importez le certificat d’ac racine pour le certificat émis sur votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez le faire à l’aide du service d’autorité de certification qui s’exécute sur l’ordinateur Active Directory cloud Connector comme suit :
    
   - Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire, ou créez un modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, voir [Modèles de certificat.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - Demandez un certificat à l’aide du logiciel en ligne Certificat en sélectionnant le modèle de serveur Web que vous avez activé. Veillez à ajouter le nom commun dans l’objet et le nom DNS dans l’autre nom avec le nom de domaine complet de la passerelle, et confirmez sur la clé privée que Rendre la clé privée exportable est sélectionné sous les options de clé. 
    
4. Exportez le certificat SSL avec une clé privée et suivez les instructions de votre fournisseur de passerelle PSTN pour importer le certificat.
    
## <a name="update-the-domain-for-your-tenant"></a>Mettre à jour le domaine pour votre client

Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Microsoft 365 ou Office 365, voir Ajouter un domaine à Microsoft 365 [ou Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Ajouter des enregistrements DNS pour votre edge

Ajoutez les enregistrements DNS suivants à Microsoft 365 ou Office 365 organisation. Pour plus d’informations sur l’ajout d’enregistrements DNS, voir Ajouter ou modifier des enregistrements [DNS](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)personnalisés dans Microsoft 365 ou Office 365 .
  
1. Ajoutez un enregistrement DNS A pour le edge d’accès.
    
2. Les enregistrements SRV sont automatiquement créés par Microsoft 365 ou Office 365 et les scripts de déploiement. Confirmez que vous pouvez rechercher les deux services SIP suivants sur le edge : sip et \_ \_ sipfederationtls.
    
     ![Confirmation des enregistrements SRV.](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configurer la connectivité hybride entre Cloud Connector Edition et Microsoft 365 ou Office 365

Pour configurer la connectivité hybride entre votre déploiement Skype Entreprise Cloud Connector Edition et votre organisation Microsoft 365 ou Office 365, exécutez l’cmdlet suivante dans une session PowerShell distante. Pour découvrir comment établir une session PowerShell distante, voir : Configurer votre ordinateur [pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
L’cmdlet définit le FQDN externe du edge d’accès. Dans la première des commandes, celle-ci doit être celle du rôle \<External Access Edge FQDN\> Edge d’accès SIP. Par défaut, ce doit être ap. \<Domain Name\> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Le FQDN du edge d’accès externe utilisé pour la destination homologue doit être affecté à un site PSTN qui sera uniquement utilisé comme base au cas où un utilisateur n’est pas affecté à un site PSTN. Pour plus d’informations, voir [Déployer un seul site dans Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et Déployer plusieurs sites dans Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>Configurer des passerelles PSTN

Configurer des trunks sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation pour toutes les appliances. Chaque trunk doit pointer vers un nom de groupe ou une adresse IP du serveur de médiation au lieu du nom de pool de serveurs de médiation, car le nom de pool est le même pour tous les serveurs du pool. Les trunks doivent être définies dans la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devez configurer les passerelles et les serveurs de médiation pour prendre en charge MTLS comme suit :
  
1. Exporte l’autorité de contrôle d’autorité de contrôle racine à partir de l’ordinateur Active Directory cloud Connector.
    
2. Suivez les instructions du fournisseur de passerelle PSTN pour importer l’ac racine.
    
3. Importez le certificat d’ac racine pour le certificat émis sur votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez le faire à l’aide du service d’autorité de certification qui s’exécute sur l’ordinateur Active Directory cloud Connector comme suit :
    
   - Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, voir [Modèles de certificat.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - Demandez un certificat à l’aide du logiciel en ligne Certificat en sélectionnant le modèle de serveur Web que vous avez activé. Veillez à ajouter le nom commun dans l’objet et le nom DNS dans l’autre nom avec le nom de domaine complet de la passerelle, et confirmez sur la clé privée que Rendre la clé privée exportable est sélectionné sous les options de clé. 
    
4. Exportez le certificat SSL avec une clé privée et suivez les instructions de votre fournisseur de passerelle PSTN pour importer le certificat.
    
5. Les passerelles PSTN d’un site PSTN ne doivent se connecter qu’aux serveurs de médiation du même site.
    
## <a name="set-up-your-users"></a>Configurer vos utilisateurs

Connectez-vous au Centre d’administration Microsoft 365, ajoutez les utilisateurs qui seront activés pour les services vocaux en ligne et attribuez une licence E5 ou un module Système téléphonique à ces utilisateurs. Pour plus d’informations sur l’ajout d’utilisateurs, [voir Ajouter des utilisateurs à Microsoft 365 entreprise.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Activer les utilisateurs pour Système téléphonique services vocaux et de messagerie vocale
 
Après avoir ajouté vos utilisateurs à Microsoft 365 ou Office 365, activez leurs comptes pour Système téléphonique services vocaux, y compris la messagerie vocale. Pour activer ces fonctionnalités, vous devez vous connecter à votre organisation Microsoft 365 ou Office 365 avec un compte qui est un rôle d’administrateur général et être en mesure d’exécuter PowerShell à distance. Pour découvrir comment établir une session PowerShell distante, voir : Configurer votre ordinateur pour [Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- Affectez la stratégie à votre utilisateur et configurez le numéro de téléphone vocal de l’utilisateur, que vous spécifiez avec la valeur du **paramètre Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Une identité d’utilisateur peut être spécifiée à l’aide de l’adresse SIP de l’utilisateur, du nom d’utilisateur principal (UPN) ou du nom complet Active Directory de l’utilisateur (par exemple, « Bob Kelly »). Le caractère astérisque ( ) peut également être utilisé avec le nom complet comme \* identité de l’utilisateur. Par exemple, l’identité « Smith » renvoie tous les utilisateurs dont le nom complet se termine par la valeur de chaîne \* « Smith ».
  
Vous pouvez ensuite vérifier que les utilisateurs ont été ajoutés et activés à l’aide du script suivant :
  
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

Vous devez décider si vos utilisateurs doivent être en mesure d’effectuer des appels internationaux. Par défaut, les appels internationaux sont activés. Vous pouvez désactiver ou activer les utilisateurs pour la numérotation internationale à l’aide du centre d’administration Skype Entreprise en ligne.
  
Pour désactiver les appels internationaux par utilisateur, exécutez l’cmdlet suivante dans Skype Entreprise Online PowerShell :
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Pour réactiver les appels internationaux par utilisateur après sa désactivation, exécutez la même cmdlet, mais modifiez la valeur de **PolicyName** en *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Affecter des utilisateurs à des sites PSTN

Utilisez powerShell distant client pour affecter un site aux utilisateurs, même si vous avez déployé un seul site. Pour découvrir comment établir une session PowerShell distante, voir : Configurer votre ordinateur [pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Si aucun site PSTN n’est affecté à un utilisateur, la connectivité hybride entre votre déploiement Skype Entreprise Cloud Connector Edition et votre organisation Microsoft 365 ou Office 365 revient à utiliser le niveau de client par défaut 1 (destination homologue) afin que les appels soient terminés. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurer le serveur de médiation hybride en ligne Paramètres
<a name="BKMK_ConfigureMediationServer"> </a>

Lorsqu’un appel P2P est recalcalé à une conférence PSTN, le serveur de conférence Skype Entreprise Online envoie une invitation au serveur de médiation Cloud Connector. Pour vous assurer que Microsoft 365 ou Office 365 pouvez router cette invitation correctement, vous devez configurer un paramètre dans votre client en ligne pour chaque serveur de médiation Cloud Connector comme suit : 
  
1. Créez un utilisateur dans le Centre d’administration Microsoft 365. Utilisez le nom d’utilisateur que vous souhaitez, tel que « MediationServer1 ».
    
    Utilisez le domaine SIP par défaut de Cloud Connector (le premier domaine SIP du fichier .ini) comme domaine utilisateur.
    
    Veuillez noter que l’attribution de licence n’est requise que pour la propagation de l’utilisateur dans Skype Entreprise répertoire en ligne. Attribuez une licence Microsoft 365 ou Office 365 (par exemple, E5) au compte que vous créez, autorisez jusqu’à une heure pour que les modifications se propagent, vérifiez que les comptes d’utilisateur ont été correctement mis en service dans l’annuaire en ligne Skype Entreprise en exécutant la cmdlet suivante, puis supprimez la licence de ce compte.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Démarrez une session PowerShell distante Azure AD client à l’aide de vos informations d’identification d’administrateur global ou utilisateur, puis exécutez l’cmdlet suivante pour définir le service du compte d’utilisateur Azure AD configuré à l’étape 1 sur « HybridMediationServer » :

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Démarrez une session PowerShell distante Skype Entreprise client à l’aide de vos informations d’identification d’administrateur client Skype Entreprise, puis exécutez l’cmdlet suivante pour définir le nom de domaine complet du serveur de médiation et du serveur Edge sur ce compte d’utilisateur, en remplaçant par le nom d’affichage de l’utilisateur pour le compte que vous avez créé à l’étape \<DisplayName\> 1 :
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Pour l’identité, utilisez le nom complet du compte d’utilisateur que vous avez créé pour ce serveur de médiation.
    
    Pour  *mediationServerFQDN,*  utilisez le nom de groupe interne défini pour votre serveur de médiation.
    
    Pour  *edgeServerExternalFQDN,*  utilisez le FQDN externe défini pour le proxy d’accès au serveur Edge. S’il existe plusieurs sites PSTN Cloud Connector, choisissez le FQDN du proxy d’accès du serveur Edge affecté au site où se trouve le serveur de médiation.
    
4. S’il existe plusieurs serveurs de médiation Cloud Connector (plusieurs sites, haute haute qualité), répétez les étapes précédentes pour chacun d’eux.
