---
title: Configuration de l’intégration de Cloud Connector à votre organisation Microsoft 365 ou Office 365
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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Découvrez comment configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365.
ms.openlocfilehash: 2c65551ce75efce61f82d47ac2b9c16db555ab42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221244"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configuration de l’intégration de Cloud Connector à votre organisation Microsoft 365 ou Office 365
 
Découvrez comment configurer l’intégration de Cloud Connector avec votre organisation Microsoft 365 ou Office 365.
  
Une fois l’installation de Skype entreprise, version Cloud Connector terminée, effectuez les étapes de cette section pour configurer votre déploiement et le connecter à votre organisation Microsoft 365 ou Office 365.
  
## <a name="configure-firewall-settings"></a>Configurer les paramètres de pare-feu

Configurez les paramètres de pare-feu pour vos paramètres de pare-feu interne et externe pour votre réseau de périmètre afin d’ouvrir les ports requis comme décrit dans la section [ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) de la rubrique [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurer des passerelles de réseau téléphonique commuté (PSTN)

Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation pour toutes les appliances. Étant donné que le nom de domaine complet du pool est le même pour tous les serveurs du pool, chaque jonction doit pointer vers un nom de domaine complet du serveur de médiation ou une adresse IP au lieu du nom de domaine complet du pool de serveurs de médiation. Les jonctions doivent être définies dans la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’autorité de certification racine à partir de l’ordinateur Active Directory du Cloud Connector.
    
2. Suivez les instructions du fournisseur de la passerelle PSTN pour importer l’autorité de certification racine.
    
3. Importez le certificat de l’autorité de certification racine pour le certificat délivré à votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez le faire à l’aide du service de l’autorité de certification qui s’exécute sur l’ordinateur Active Directory du Cloud Connector comme suit :
    
   - Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, consultez la rubrique [modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Demandez un certificat à l’aide du composant logiciel enfichable certificat en sélectionnant le modèle de serveur Web que vous avez activé. N’oubliez pas d’ajouter nom commun dans objet et nom DNS dans la zone autre nom avec le nom de domaine complet de la passerelle, et vérifiez sur la clé privée que la clé privée exportable est sélectionnée sous options de clé. 
    
4. Exportez le certificat SSL avec la clé privée et suivez les instructions de votre fournisseur de passerelle PSTN pour importer le certificat.
    
## <a name="update-the-domain-for-your-tenant"></a>Mettre à jour le domaine pour votre client

Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la configuration de votre domaine dans Microsoft 365 ou Office 365, consultez la rubrique [Ajouter un domaine à microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Ajouter des enregistrements DNS pour votre serveur Edge

Ajoutez les enregistrements DNS suivants à votre organisation Microsoft 365 ou Office 365. Pour plus d’informations sur l’ajout d’enregistrements DNS, consultez la rubrique [Ajouter ou modifier des enregistrements DNS personnalisés dans Microsoft 365 ou Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Ajoutez un enregistrement DNS A pour le serveur Edge d’accès.
    
2. Les enregistrements SRV seront automatiquement créés par Microsoft 365 ou Office 365 et les scripts de déploiement. Vérifiez que vous pouvez rechercher les deux services SIP suivants sur le serveur Edge : \_ SIP et \_ sipfederationtls.
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configuration de la connectivité hybride entre Cloud Connector Edition et Microsoft 365 ou Office 365

Pour configurer la connectivité hybride entre votre déploiement Skype entreprise version Cloud Connector et votre organisation Microsoft 365 ou Office 365, exécutez l’applet de commande suivante dans une session PowerShell distante. Pour savoir comment établir une session PowerShell à distance, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
L’applet de commande définit le nom de domaine complet externe du serveur Edge d’accès. Dans la première des commandes, le \< nom de domaine complet du serveur Edge d’accès externe \> doit être celui du rôle de serveur Edge d’accès SIP. Par défaut, il doit s’agir de AP. \< Nom de domaine \> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Le nom de domaine complet du serveur Edge d’accès externe utilisé pour la destination de l’homologue doit être défini sur un site RTC qui sera utilisé uniquement comme serveur de secours si un utilisateur n’est pas affecté à un site RTC. Pour plus d’informations, reportez-vous à [la rubrique deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et [Deploy Multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurer des passerelles RTC

Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation pour toutes les appliances. Chaque jonction doit pointer vers un nom de domaine complet du serveur de médiation ou une adresse IP au lieu du nom de domaine complet du pool de serveurs de médiation, car le nom de domaine complet du pool est le même pour tous les serveurs du pool. Les jonctions doivent être définies dans la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’autorité de certification racine à partir de l’ordinateur Active Directory du Cloud Connector.
    
2. Suivez les instructions du fournisseur de la passerelle PSTN pour importer l’autorité de certification racine.
    
3. Importez le certificat de l’autorité de certification racine pour le certificat délivré à votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez le faire à l’aide du service de l’autorité de certification qui s’exécute sur l’ordinateur Active Directory du Cloud Connector comme suit :
    
   - Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, consultez la rubrique [modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Demandez un certificat à l’aide du composant logiciel enfichable certificat en sélectionnant le modèle de serveur Web que vous avez activé. N’oubliez pas d’ajouter nom commun dans objet et nom DNS dans la zone autre nom avec le nom de domaine complet de la passerelle, et vérifiez sur la clé privée que la clé privée exportable est sélectionnée sous options de clé. 
    
4. Exportez le certificat SSL avec la clé privée et suivez les instructions de votre fournisseur de passerelle PSTN pour importer le certificat.
    
5. La ou les passerelles PSTN dans un site RTC doivent se connecter uniquement au (x) serveur (s) de médiation dans le même site.
    
## <a name="set-up-your-users"></a>Configurer vos utilisateurs

Connectez-vous au centre d’administration Microsoft 365, ajoutez les utilisateurs qui seront activés pour les services vocaux en ligne et attribuez une licence ou un module complémentaire de système téléphonique E5 à la licence E3 pour ces utilisateurs. Pour plus d’informations sur l’ajout d’utilisateurs, consultez la rubrique [Ajouter des utilisateurs à Microsoft 365 pour les entreprises](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Activer les services vocaux et de messagerie vocale du système téléphonique
 
Après avoir ajouté vos utilisateurs à Microsoft 365 ou Office 365, activez leur compte pour les services vocaux de système téléphonique, y compris la messagerie vocale. Pour activer ces fonctionnalités, vous devez vous connecter à votre organisation Microsoft 365 ou Office 365 à l’aide d’un compte qui est un rôle d’administrateur général et être en mesure d’exécuter PowerShell à distance. Pour savoir comment établir une session PowerShell à distance, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- Affectez la stratégie à votre utilisateur et configurez le numéro de téléphone voix entreprise de l’utilisateur, que vous spécifiez avec la valeur du paramètre **Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Une identité d’utilisateur peut être spécifiée à l’aide de l’adresse SIP de l’utilisateur, du nom d’utilisateur principal (UPN) ou du nom complet Active Directory de l’utilisateur (par exemple, « Bob Kelly »). Le caractère astérisque ( \* ) peut également être utilisé avec le nom d’affichage comme identité de l’utilisateur. Par exemple, l’identité « \* Smith » renvoie tous les utilisateurs dont le nom complet se termine par la valeur de chaîne « Smith ».
  
Vous pouvez ensuite vérifier que les utilisateurs ont été ajoutés et activés à l’aide du script suivant :
  
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

Vous devez décider si vos utilisateurs doivent être en mesure d’effectuer des appels internationaux. Par défaut, les appels internationaux sont activés. Vous pouvez désactiver ou activer les utilisateurs pour la numérotation internationale à l’aide du centre d’administration Skype entreprise online.
  
Pour désactiver les appels internationaux au niveau de chaque utilisateur, exécutez l’applet de commande suivante dans Skype entreprise Online PowerShell :
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Pour réactiver les appels internationaux au niveau de chaque utilisateur une fois qu’il a été désactivé, exécutez la même cmdlet, mais modifiez la valeur de **PolicyName** sur *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Affecter des utilisateurs à des sites PSTN

Utilisez un PowerShell distant du client pour affecter un site aux utilisateurs, même si vous n’avez déployé qu’un seul site. Pour savoir comment établir une session PowerShell à distance, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Si aucun site PSTN n’est affecté à un utilisateur, la connectivité hybride entre votre déploiement Skype entreprise et votre organisation Microsoft 365 ou Office 365 revient à utiliser le niveau client par défaut (destination de l’homologue) de sorte que les appels puissent être menés à bien. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurer les paramètres de serveur de médiation hybride en ligne
<a name="BKMK_ConfigureMediationServer"> </a>

Lorsqu’un appel P2P est remonté vers une conférence RTC, le serveur de conférence Skype entreprise Online enverra une invitation au serveur de médiation Cloud Connector. Pour vous assurer que Microsoft 365 ou Office 365 peut acheminer cette invitation correctement, vous devez configurer un paramètre dans votre client en ligne pour chaque serveur de médiation Cloud Connector comme suit : 
  
1. Créez un utilisateur dans le centre d’administration Microsoft 365. Utilisez le nom d’utilisateur de votre choix, par exemple « MediationServer1 ».
    
    Utilisez le domaine SIP par défaut de Cloud Connector (le premier domaine SIP du fichier. ini) en tant que domaine de l’utilisateur.
    
    Veuillez noter que l’attribution de licence n’est requise que pour la propagation de l’utilisateur dans le répertoire Skype entreprise online. Affecter une licence Microsoft 365 ou Office 365 (par exemple, E5) au compte que vous créez, autoriser jusqu’à une heure pour que les modifications soient propagées, vérifier que les comptes d’utilisateur ont été correctement configurés dans l’annuaire Skype entreprise Online en exécutant l’applet de commande suivante, puis supprimer la licence de ce compte.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Démarrez une session PowerShell client Azure AD à l’aide de vos informations d’identification d’administrateur ou d’utilisateur, puis exécutez l’applet de commande suivante pour définir le service pour le compte d’utilisateur Azure AD configuré à l’étape 1 sur « HybridMediationServer » :

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Démarrez une session PowerShell client Skype entreprise à l’aide de vos informations d’identification d’administrateur client Skype entreprise, puis exécutez l’applet de commande suivante pour définir le nom de domaine complet du serveur de médiation et du serveur Edge sur ce compte d’utilisateur, en remplaçant \< DisplayName \> par le nom complet de l’utilisateur pour le compte que vous avez créé à l’étape 1 :
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Pour Identity, utilisez le nom d’affichage du compte d’utilisateur que vous avez créé pour ce serveur de médiation.
    
    Pour *MediationServerFQDN* , utilisez le nom de domaine complet interne défini pour votre serveur de médiation.
    
    Pour *EdgeServerExternalFQDN* , utilisez le nom de domaine complet externe défini pour le proxy d’accès du serveur Edge. S’il existe plusieurs sites RTC Cloud Connector, choisissez le nom de domaine complet du proxy d’accès du serveur Edge affecté au site où se trouve le serveur de médiation.
    
4. S’il existe plusieurs serveurs de médiation Cloud Connector (multisite, haute disponibilité), répétez les étapes précédentes pour chacun d’eux.
    
