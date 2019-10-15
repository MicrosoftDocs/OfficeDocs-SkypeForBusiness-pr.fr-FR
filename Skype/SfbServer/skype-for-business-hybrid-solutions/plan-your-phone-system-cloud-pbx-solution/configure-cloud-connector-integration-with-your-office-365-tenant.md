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
ms.openlocfilehash: b4c70c5698601a2aa69669da3384b6806af98110
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37508809"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configure Cloud Connector integration with your Office 365 tenant
 
Apprenez à configurer l’intégration du connecteur Cloud à votre client Office 365.
  
Une fois l’installation de Skype Entreprise, version Cloud Connector achevée, les étapes décrites dans cette rubrique vous permettront de configurer votre déploiement et de le connecter à votre client Office 365.
  
## <a name="configure-firewall-settings"></a>Configurer les paramètres du pare-feu

Configurez les paramètres de pare-feu pour votre réseau de périmètre pour l’ouverture des ports requis, comme décrit dans la rubrique [ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) du [plan de Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configuration de passerelles PSTN (réseau téléphonique commuté)

Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.
    
2. Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.
    
3. Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :
    
   - Modifiez le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés de s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, voir [modèles de certificats](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
   - Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé. Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé. 
    
4. Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.
    
## <a name="update-the-domain-for-your-tenant"></a>Mettez à jour le domaine pour votre client

Assurez-vous d’avoir accompli les étapes pour mettre à jour votre domaine dans Office 365 et d’avoir la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la configuration de votre domaine dans Office 365, voir [Ajouter un domaine à office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Ajouter des enregistrements dans Office 365 pour Edge

Ajoutez les enregistrements DNS suivants à votre client Office 365. Pour plus d’informations sur l’ajout d’enregistrements DNS à votre client 365 Office, voir [Ajouter ou modifier des enregistrements DNS personnalisés dans Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Ajouter un enregistrement DNS A pour le serveur Edge d’accès.
    
2. Les enregistrements SRV seront automatiquement créés par Office 365 et les scripts de déploiement. Vérifiez que vous pouvez voir les deux services SIP suivants sur Edge : _sip et _sipfederationtls.
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configurationd’une connectivité hybride entre la version Cloud Connector et Office 365

Pour configurer une connectivité hybride entre le déploiement de Skype entreprise version Cloud Connector et votre client Office 365, exécutez l’applet de commande suivante dans une session PowerShell distante. Pour plus d’informations sur l’établissement d’une session PowerShell distante, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
L’applet de commande définit le FQDN externe du serveur Edge d’accès. Dans la première des commandes, le \<nom de domaine complet\> du périmètre d’accès externe doit être celui du rôle de périmètre d’accès SIP. Par défaut, il doit s’agir du\<nom\>d’accès du domaine.
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Le nom de domaine complet du périmètre d’accès externe utilisé pour la destination homologue doit être défini sur un site PSTN qui sera utilisé uniquement comme secours au cas où un utilisateur n’est pas attribué à un site PSTN. Pour plus d’informations, reportez-vous à la rubrique [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) et [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurer les passerelles RTC

Configurez les jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.
    
2. Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.
    
3. Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :
    
   - Modifiez le modèle du serveur Web existant pour autoriser les utilisateurs authentifiés à s’inscrire, ou créez un nouveau modèle de serveur Web pour configurer d’autres propriétés et autoriser les utilisateurs authentifiés à s’inscrire. Pour obtenir des instructions détaillées, voir [modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé. Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé. 
    
4. Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.
    
5. La ou les passerelle(s) RTC d’un site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site.
    
## <a name="set-up-your-users-in-office-365"></a>Configurez vos utilisateurs dans Office 365

Connectez-vous au portail d’administration Office 365, ajoutez les utilisateurs qui seront activés pour les services vocaux en ligne et attribuez une licence ou un système téléphonique E5 dans le module complémentaire Office 365 à la licence E3 pour ces utilisateurs. Pour plus d’informations sur l’ajout d’utilisateurs, voir [Ajouter des utilisateurs à Office 365 pour les entreprises](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Permettre aux utilisateurs de système téléphonique dans Office 365 des services vocaux et de messagerie vocale

Après avoir ajouté vos utilisateurs à Office 365, activez leurs comptes pour le système téléphonique dans les services vocaux d’Office 365, y compris la boîte vocale. Pour activer ces fonctionnalités, vous devez vous connecter à votre client Office 365 avec un compte de rôle d’administrateur général Office 365, et être en mesure d’exécuter PowerShell à distance. Pour plus d’informations sur l’établissement d’une session PowerShell distante, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Affectez la stratégie à votre utilisateur et configurez le numéro de téléphone professionnel de l’utilisateur, que vous spécifiez avec la valeur du paramètre **Identity** :
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Vous pouvez spécifier une identité d’utilisateur à l’aide de l’adresse SIP de l’utilisateur, du nom d’utilisateur principal (UPN) ou du nom complet de l’utilisateur Active Directory (par exemple, « Robert Kelly »). Le caractère astérisque\*() peut également être utilisé avec le nom complet comme identité d’utilisateur. Par exemple, l’identité «\*Smith » renvoie tous les utilisateurs dont le nom d’affichage se termine par la valeur de chaîne « Dupont ».
  
Vous pouvez ensuite vérifier que les utilisateurs ont été ajoutés et activés grâce au script suivant :
  
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

Vous devrez décider d'autoriser ou non les utilisateurs à passer des appels internationaux. Par défaut, les appels internationaux sont activés. Vous pouvez activer ou désactiver les appels internationaux pour des utilisateurs grâce au centre d’administration Skype Entreprise en ligne.
  
Pour désactiver les appels internationaux au niveau de l’utilisateur, exécutez l’applet de commande suivante dans PowerShell de Skype Entreprise Online :
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Pour réactiver les appels internationaux en fonction de la manière dont elle a été désactivée, exécutez la même applet de la même façon, mais remplacez la valeur de **PolicyName** par *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Affecter les utilisateurs aux sites RTC

Utilisez PowerShell en client distant pour affecter un site aux utilisateurs, même si vous avez déployé un site unique. Pour plus d’informations sur l’établissement d’une session PowerShell distante, voir : [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Si aucun site RTC n’est affecté à un utilisateur, la connectivité hybride entre votre déploiement de la version Cloud Connector de Skype Entreprise et votre client Office 365 utilisera celui par défaut au niveau de client (destination des pairs) pour pouvoir achever les appels. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configuration des paramètres du serveur de médiation hybride en ligne
<a name="BKMK_ConfigureMediationServer"> </a>

Lorsqu’un appel P2P est transféré vers une conférence RTC, le serveur de conférence Skype entreprise Online envoie une invitation au serveur de médiation Cloud Connector. Pour vous assurer qu’Office 365 peut diriger cette invitation, vous devez configurer un paramètre dans votre client en ligne pour chaque serveur de médiation du Cloud Cloud comme suit : 
  
1. Créer un utilisateur dans le portail d’administration 365 Office. Utilisez le nom d’utilisateur de votre choix (par exemple, « MediationServer1 »).
    
    Utilisez le domaine SIP par défaut de Cloud Connector (le premier domaine SIP du fichier. ini) en tant que domaine de l’utilisateur.
    
    Veuillez noter que l’attribution de licence est uniquement requise pour la propagation de l’utilisateur dans l’annuaire Skype entreprise online. Attribution d’une licence Office 365 (par exemple, E5) au compte que vous créez, autorisant jusqu’à une heure pour que les modifications soient propagées, vérifiez que les comptes d’utilisateurs ont été correctement configurés pour le répertoire Skype entreprise Online en exécutant l’applet de commande suivante, puis supprimez le licence de ce compte.
    ```
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Démarrez une session de connexion distante Azure AD à un client à l’aide de vos informations d’identification d’administrateur général ou d’utilisateur, puis exécutez l’applet de commande suivante pour définir le service pour le compte d’utilisateur Azure AD configuré à l’étape 1 sur « HybridMediationServer » :

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Démarrez une session PowerShell à distance avec Skype entreprise à l’aide de vos informations d’identification d’administrateur de clients Skype entreprise, puis exécutez l’applet de commande suivante pour définir le nom de domaine complet \<\> du serveur de médiation avec le nom complet de l’utilisateur pour le compte que vous avez créé à l’étape 1 :
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Pour l’identité, utilisez le nom d’affichage du compte utilisateur Office 365 que vous avez créé pour ce serveur de médiation.
    
    Pour *MediationServerFQDN* , utilisez le FQDN interne défini pour votre serveur de médiation.
    
    Pour *EdgeServerExternalFQDN* , utilisez le FQDN externe défini pour le proxy d’accès Edge Server. Si plusieurs sites RTC Cloud Connector existent, choisissez le FQDN du proxy du serveur Edge d’accès affecté au site qui contient la localisation du serveur de médiation.
    
4. Si plusieurs serveurs de médiation Cloud Connector existent (plusieurs sites en haute disponibilité), veuillez répéter les étapes précédentes pour chacun d’entre eux.
    

