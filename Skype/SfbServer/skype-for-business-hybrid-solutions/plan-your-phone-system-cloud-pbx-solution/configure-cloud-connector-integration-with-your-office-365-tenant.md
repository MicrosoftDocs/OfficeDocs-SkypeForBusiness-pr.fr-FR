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
ms.custom: Strat_SB_Hybrid
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Découvrez comment configurer l’intégration de connecteur de nuage avec vos clients d’Office 365.
ms.openlocfilehash: c8e74353bc9b1201d8e4ff11f27a3542f24cb373
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configurer l’intégration Cloud Connector avec votre client Office 365
 
Découvrez comment configurer l’intégration de connecteur de nuage avec vos clients d’Office 365.
  
Une fois l’installation de Skype Entreprise, version Cloud Connector achevée, les étapes décrites dans cette rubrique vous permettront de configurer votre déploiement et de le connecter à votre client Office 365.
  
## <a name="configure-firewall-settings"></a>Configurer les paramètres du pare-feu

Configurer les paramètres du pare-feu pour les paramètres de pare-feu internes et externes de votre réseau de périmètre ouvrir les ports requis, comme décrit dans les [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) dans le [Plan de Skype pour connecteur de Cloud Business Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configuration de passerelles PSTN (réseau téléphonique commuté)

Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.
    
2. Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.
    
3. Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :
    
  - Modifier le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés s’inscrire ou créer un nouveau modèle de serveur Web pour configurer d’autres propriétés et d’activer les utilisateurs authentifiés à inscrire. Pour obtenir des instructions détaillées, voir [Modèles de certificats](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
  - Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé. Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé. Pour obtenir des instructions détaillées, reportez-vous à [demander un certificat](https://technet.microsoft.com/en-us/library/cc730689.aspx).
    
4. Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.
    
## <a name="update-the-domain-for-your-tenant"></a>Mettez à jour le domaine pour votre client

Assurez-vous d’avoir accompli les étapes pour mettre à jour votre domaine dans Office 365 et d’avoir la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, reportez-vous à la section [vidéo : définir votre domaine dans Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Ajouter des enregistrements dans Office 365 pour Edge

Ajoutez les enregistrements DNS suivants à votre client Office 365. Pour plus d’informations sur la façon d’ajouter des enregistrements DNS à vos clients d’Office 365, voir [Ajouter ou modifier des enregistrements DNS personnalisés dans Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Ajouter un enregistrement DNS A pour le serveur Edge d’accès.
    
2. Les enregistrements SRV seront automatiquement créés par Office 365 et les scripts de déploiement. Vérifiez que vous pouvez voir les deux services SIP suivants sur Edge : _sip et _sipfederationtls.
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configurationd’une connectivité hybride entre la version Cloud Connector et Office 365

Pour configurer la connectivité hybride entre votre Skype pour le déploiement de connecteur de Cloud Business Edition et vos clients Office 365, exécutez l’applet de commande suivante dans une session distante de PowerShell. Pour savoir comment établir une session PowerShell à distance, voir : [À l’aide de Windows PowerShell pour gérer Skype pour l’activité en ligne](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
L’applet de commande définit le nom de domaine complet du serveur dʼaccès Edge. Dans le premier des commandes, la \<un FQDN externe Access Edge\> doit être celle du rôle Edge d’accès SIP. Par défaut, ce doit être ap.\<nom de domaine\>.
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Le FQDN de bord accès externe utilisé pour la Destination de l’homologue doit être défini sur un site de RTPC qui sera uniquement utilisé comme un secours au cas où un utilisateur n’est pas affecté à un site RTPC. Pour plus d’informations, voir [déployer un site unique dans le connecteur du nuage](deploy-a-single-site-in-cloud-connector.md) et [déployer plusieurs sites dans le connecteur de nuage](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurer les passerelles RTC

Configurez les jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.
    
2. Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.
    
3. Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :
    
  - Modifiez le modèle Serveur web existant pour permettre aux utilisateurs authentifiés de s’inscrire ou de créer un modèle Serveur web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, voir [Modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).
    
  - Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé. Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé. Pour obtenir des instructions détaillées, reportez-vous à [demander un certificat](https://technet.microsoft.com/library/cc730689.aspx).
    
4. Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.
    
5. La ou les passerelle(s) RTC d’un site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site.
    
## <a name="set-up-your-users-in-office-365"></a>Configurez vos utilisateurs dans Office 365

Ouvrez une session le portail d’administration d’Office 365, ajoutez les utilisateurs qui seront activés pour les services en ligne et attribuer une licence de E5 ou un système téléphonique dans le module complémentaire d’Office 365 à la licence E3 à ces utilisateurs. Pour plus d’informations sur l’ajout d’utilisateurs, voir [Ajout d’utilisateurs à Office 365 pour entreprises](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Permettre aux utilisateurs de système téléphonique dans les services vocaux et de messagerie vocale d’Office 365

Après avoir ajouté vos utilisateurs vers Office 365, activer leurs comptes de système téléphonique dans les services de téléphonie Office 365, y compris la messagerie vocale. Pour activer ces fonctionnalités, vous devez vous connecter à votre client Office 365 avec un compte de rôle d’administrateur général Office 365, et être en mesure d’exécuter PowerShell à distance. Pour savoir comment établir une session PowerShell à distance, voir : [À l’aide de Windows PowerShell pour gérer Skype pour professionnels en ligne](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Affecter la stratégie à votre utilisateur et configurer voix numéro de téléphone professionnel l’utilisateur, que vous spécifiez avec la valeur du paramètre **identité** :
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Vous pouvez également spécifier l’identité d’un utilisateur par son adresse SIP, son nom d’utilisateur principal (UPN), son nom de domaine et nom d’utilisateur (domaine\nom d’utilisateur) et le nom d’affichage dans Active Directory (« Bob Kelly »).  
  
Vous pouvez vérifier que les utilisateurs ont été ajoutés et activés à l’aide du script suivant :
  
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

Vous devrez décider si vos utilisateurs peuvent passer des appels internationaux. Par défaut, les appels internationaux sont activés. Vous pouvez désactiver ou activer la numérotation internationale pour des utilisateurs à l’aide du centre d’administration Skype Entreprise Online.
  
Pour désactiver la numération internationale pour des utilisateurs spécifiques, exécutez l’applet de commande suivante dans le module Skype Entreprise Online pour PowerShell :
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Pour réactiver international d’appel sur une base par utilisateur, après que qu’elle a été désactivée, exécutez l’applet de commande même, mais remplacez la valeur de **stratégie** *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Affecter les utilisateurs aux sites RTC

Utilisez PowerShell en client distant pour affecter un site aux utilisateurs, même si vous avez déployé un site unique. Pour savoir comment établir une session PowerShell à distance, voir : [À l’aide de Windows PowerShell pour gérer Skype pour l’activité en ligne](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
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

Lors d’un appel de P2P est remonté à une conférence PSTN, le Skype pour Business Online conferencing server envoie une invitation pour le serveur de médiation de connecteur de nuage. Pour vous assurer qu’Office 365 peut acheminer cette invitation avec succès, vous devez configurer un paramètre de vos clients en ligne pour chaque serveur de médiation de connecteur de nuage, comme suit : 
  
1. Créer un utilisateur dans le portail d’administration d’Office 365. Utilisez n’importe quel nom d’utilisateur, par exemple « MediationServer1 ».
    
    Utiliser le domaine SIP par défaut du connecteur de Cloud (le premier domaine SIP dans le fichier .ini) comme le domaine de l’utilisateur.
    
    N’affectez aucune licence Office 365 (comme E5) au compte que vous créez. Attendez que la synchronisation de l’AD et d’Office 365 soit terminée.
    
2. Démarrer une session PowerShell distante de clients à l’aide de vos informations d’identification administrateur de clients et puis exécutez l’applet de commande suivante pour définir le serveur de médiation et le FQDN du serveur Edge à cet utilisateur de compte, remplaçant \<DisplayName\> avec le nom complet de l’utilisateur pour le compte créé :
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    Pour l’identité, utilisez le nom d’affichage du compte utilisateur Office 365 que vous avez créé pour ce serveur de médiation.
    
    Pour *MediationServerFQDN* , utilisez le nom de domaine complet interne défini pour votre serveur de médiation.
    
    Pour *EdgeServerExternalFQDN* , utilisez le FQDN externe défini pour le Proxy d’accès serveur Edge. Si plusieurs sites RTC Cloud Connector existent, choisissez le FQDN du proxy du serveur Edge d’accès affecté au site qui contient la localisation du serveur de médiation.
    
3. Si plusieurs serveurs de médiation Cloud Connector existent (plusieurs sites en haute disponibilité), veuillez répéter les étapes précédentes pour chacun d’entre eux.
    

