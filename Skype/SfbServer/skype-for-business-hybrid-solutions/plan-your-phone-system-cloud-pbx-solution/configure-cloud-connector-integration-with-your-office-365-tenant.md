---
title: Configurer l’intégration Cloud Connector avec votre client Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Découvrez comment configurer l’intégration de nuage connecteur avec votre client Office 365.
ms.openlocfilehash: 40cb3334fb3d45432ada1a63aae8368a60433ad0
ms.sourcegitcommit: 6340d0050a51790e40b7ab8e4e89348251ba184f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/06/2018
ms.locfileid: "19649642"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configurer l’intégration Cloud Connector avec votre client Office 365
 
Découvrez comment configurer l’intégration de nuage connecteur avec votre client Office 365.
  
Une fois l’installation de Skype Entreprise, version Cloud Connector achevée, les étapes décrites dans cette rubrique vous permettront de configurer votre déploiement et de le connecter à votre client Office 365.
  
## <a name="configure-firewall-settings"></a>Configurer les paramètres du pare-feu

Configurer les paramètres de pare-feu pour les paramètres de pare-feu internes et externes de votre réseau de périmètre ouvrir les ports requis, comme décrit dans les [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) dans [planifier Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configuration de passerelles PSTN (réseau téléphonique commuté)

Configurez des jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.
    
2. Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.
    
3. Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :
    
  - Modifier le modèle de serveur Web existant pour permettre aux utilisateurs authentifiés d’inscrire ou créer un nouveau modèle de serveur Web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, voir [Modèles de certificats](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
  - Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé. Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé. Pour obtenir des instructions détaillées, voir [demander un certificat](https://technet.microsoft.com/en-us/library/cc730689.aspx).
    
4. Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.
    
## <a name="update-the-domain-for-your-tenant"></a>Mettez à jour le domaine pour votre client

Assurez-vous d’avoir accompli les étapes pour mettre à jour votre domaine dans Office 365 et d’avoir la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, voir [vidéo : configurer votre domaine dans Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Ajouter des enregistrements dans Office 365 pour Edge

Ajoutez les enregistrements DNS suivants à votre client Office 365. Pour plus d’informations sur la façon d’ajouter des enregistrements DNS pour votre client Office 365, voir [Ajouter ou modifier des enregistrements DNS personnalisés dans Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Ajouter un enregistrement DNS A pour le serveur Edge d’accès.
    
2. Les enregistrements SRV seront automatiquement créés par Office 365 et les scripts de déploiement. Vérifiez que vous pouvez voir les deux services SIP suivants sur Edge : _sip et _sipfederationtls.
    
     ![Confirmation des enregistrements SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configurationd’une connectivité hybride entre la version Cloud Connector et Office 365

Pour configurer la connectivité hybride entre votre Skype pour le déploiement dans le nuage connecteur Édition et votre client Office 365, exécutez l’applet de commande suivante dans une session PowerShell distante. Pour savoir comment établir une session PowerShell distante, voir : [À l’aide de Windows PowerShell pour gérer Skype pour Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
L’applet de commande définit le nom de domaine complet du serveur dʼaccès Edge. Dans la première des commandes, le \<externe Access Edge FQDN\> doit être l’un pour le rôle de serveur Edge d’accès SIP. Par défaut, il doit s’agir ap.\<nom de domaine\>.
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> Externe Access Edge nom de domaine complet utilisé pour la Destination de l’homologue doit être défini à un site PSTN qui sera uniquement utilisé comme un secours au cas où un utilisateur n’est pas affecté à un site PSTN. Pour plus d’informations, voir [déployer un seul site dans le nuage connecteur](deploy-a-single-site-in-cloud-connector.md) et le [déploiement de plusieurs sites dans le nuage connecteur](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurer les passerelles RTC

Configurez les jonctions sur chaque passerelle PSTN pour qu’elles pointent vers les serveurs de médiation dans toutes les appliances. Chaque jonction doit pointer vers le FQDN ou l’adresse IP d’un seul serveur de médiation et non vers le FQDN du pool du serveur de médiation car le FQDN du pool est le même pour tous les serveurs du pool. Les jonctions doivent être configurées avec la même priorité.
  
Si vous utilisez TLS entre les serveurs de médiation et les passerelles, vous devrez configurer les passerelles et les serveurs de médiation pour qu’ils prennent en charge MTLS comme suit :
  
1. Exportez l’AC racine depuis l’ordinateur Active Directory du Cloud Connector.
    
2. Pour importer l’AC racine, suivez les instructions pour fournisseur de passerelle PSTN.
    
3. Importez le certificat de l’AC racine pour le certificat délivré pour votre passerelle sur les serveurs de médiation. Si vous avez besoin d’obtenir un certificat SSL pour la passerelle, vous pouvez utiliser le service de certification de l’ordinateur ActivePSTNDirectory du CloudPSTNConnector comme suit :
    
  - Modifiez le modèle Serveur web existant pour permettre aux utilisateurs authentifiés de s’inscrire ou de créer un modèle Serveur web pour configurer d’autres propriétés et permettre aux utilisateurs authentifiés de s’inscrire. Pour obtenir des instructions détaillées, voir [Modèles de certificats](https://technet.microsoft.com/library/cc730705.aspx).
    
  - Demandez un certificat à l’aide du composant logiciel enfichable Certificats, en sélectionnant le modèle de serveur Web que vous avez autorisé. Assurez-vous d’indiquer le nom commun dans la section Sujet et le nom DNS dans la section Nom alternatif avec le FQDN de la passerelle, et confirmez sur la Clé privée que Rendre la clé privée exportable est bien sélectionné dans les options de clé. Pour obtenir des instructions détaillées, voir [demander un certificat](https://technet.microsoft.com/library/cc730689.aspx).
    
4. Exportez le certificat SSL avec la Clé privée et suivez les instructions depuis votre fournisseur de passerelle RTC pour importer le certificat.
    
5. La ou les passerelle(s) RTC d’un site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site.
    
## <a name="set-up-your-users-in-office-365"></a>Configurez vos utilisateurs dans Office 365

Ouvrez une session le portail d’administration d’Office 365, ajoutez les utilisateurs qui seront activés pour les services en ligne, puis d’affecter une licence E5 ou un système téléphonique dans Office 365 module complémentaire à la licence E3 à ces utilisateurs. Pour plus d’informations sur l’ajout d’utilisateurs, voir [Ajouter des utilisateurs à Office 365 pour entreprises](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Permettre aux utilisateurs pour le système téléphonique dans les services voix et de la messagerie vocale d’Office 365

Après avoir ajouté vos utilisateurs vers Office 365, activer leur compte de système téléphonique dans les services de téléphonie Office 365, y compris la messagerie vocale. Pour activer ces fonctionnalités, vous devez vous connecter à votre client Office 365 avec un compte de rôle d’administrateur général Office 365, et être en mesure d’exécuter PowerShell à distance. Pour savoir comment établir une session PowerShell distante, voir : [À l’aide de Windows PowerShell pour gérer Skype pour Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Attribuer la stratégie à l’utilisateur et configurez vocale numéro de téléphone professionnel l’utilisateur, que vous pouvez spécifier avec la valeur du paramètre **Identity** :
    
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

Pour réactiver international l’appel sur chaque utilisateur une fois qu’il a été désactivé, exécutez l’applet de commande même, mais remplacez la valeur de **PolicyName** *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Affecter les utilisateurs aux sites RTC

Utilisez PowerShell en client distant pour affecter un site aux utilisateurs, même si vous avez déployé un site unique. Pour savoir comment établir une session PowerShell distante, voir : [À l’aide de Windows PowerShell pour gérer Skype pour Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
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

Lorsqu’un appel P2P est transmis à une conférence PSTN, le Skype pour le serveur de conférence en ligne Business envoie une invitation au serveur de médiation de connecteur dans le nuage. Pour vous assurer qu’Office 365 peut acheminer cette invitation avec succès, vous devez configurer un paramètre de votre client en ligne pour chaque serveur de médiation dans le nuage connecteur comme suit : 
  
1. Créer un utilisateur dans le portail d’administration d’Office 365. Utilisez n’importe quel nom d’utilisateur, tel que « MediationServer1 ».
    
    Utilisez le domaine SIP par défaut du nuage connecteur (le premier domaine SIP dans le fichier .ini) en tant que le domaine de l’utilisateur.
    
    Attribuer une licence Office 365 (par exemple, E5) pour le compte que vous créez.
    
2. Démarrer une session PowerShell distante de client à l’aide de votre client les informations d’identification d’administration, puis exécutez l’applet de commande suivante pour définir le serveur de médiation et le FQDN du serveur Edge à cet utilisateur de compte, remplaçant \<DisplayName\> avec le nom complet de l’utilisateur pour le vous avez créé de compte :
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    Pour l’identité, utilisez le nom d’affichage du compte utilisateur Office 365 que vous avez créé pour ce serveur de médiation.
    
    Pour *MediationServerFQDN* , utilisez le nom de domaine complet interne définie pour votre serveur de médiation.
    
    Pour *EdgeServerExternalFQDN* , utilisez le nom de domaine complet externe définie pour le Proxy d’accès serveur Edge. Si plusieurs sites RTC Cloud Connector existent, choisissez le FQDN du proxy du serveur Edge d’accès affecté au site qui contient la localisation du serveur de médiation.
    
3. Si plusieurs serveurs de médiation Cloud Connector existent (plusieurs sites en haute disponibilité), veuillez répéter les étapes précédentes pour chacun d’entre eux.
    

