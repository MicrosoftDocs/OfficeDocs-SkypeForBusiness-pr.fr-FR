---
title: Direct Routing SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur le routage direct, comme la configuration, les décisions de déploiement essentielles nécessaires et les considérations relatives au routage vocal.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c25299a0f0df6863bcb1fbaa4627b891a6e860a
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536755"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Appliance de branche (SBA) survivable pour le routage direct


Parfois, un site client utilisant le routage direct pour se connecter Téléphone Microsoft système informatique peut être en panne sur Internet.

Supposons que le site du client (appelé branche) ne puisse pas se connecter temporairement au cloud Microsoft via un routage direct. Toutefois, l’intranet à l’intérieur de la branche est toujours pleinement fonctionnel et les utilisateurs peuvent se connecter au contrôleur de session en bordure (SBC) qui fournit la connectivité PSTN.

Cet article décrit comment utiliser une appliance de branche permettant de survivre pour permettre à Téléphone Microsoft System de continuer à passer et recevoir des appels de réseau téléphonique commuté (PSTN) en cas de panne.

## <a name="prerequisites"></a>Conditions préalables

Le code SBA est le code distribuable fourni par Microsoft à des fournisseurs SBC qui incorporent ensuite du code dans leur microprogramme ou le distribuez séparément pour que SBA soit exécuté sur une version VM ou un matériel distinct. 

Pour obtenir la dernière version du microprogramme du contrôleur de session en bordure avec l’appliance de branche survivable incorporée, contactez votre fournisseur SBC. De plus, les suivantes sont obligatoires :

- Le SBC doit être configuré pour la dérivation média pour s’assurer que le client Microsoft Teams dans le site de branche peut faire circuler du média directement avec le SBC. 

- TLS1.2 doit être activé sur le système d’exploitation VM SBA.
- Les ports 3443, 4444 et 8443 sont utilisés par Microsoft SBA Server pour communiquer avec le client Teams et doivent être autorisés sur le pare-feu. 
- Le port 5061 (ou celui configuré sur le SBC) est utilisé par Microsoft SBA Server pour communiquer avec le SBC et doit être autorisé par le pare-feu. 
- Le port UDP 123 est utilisé par Microsoft SBA Server pour communiquer avec le serveur NTP et doit être autorisé par le pare-feu.
- Le port 443 est utilisé par Microsoft SBA Server pour communiquer avec les Microsoft 365 et doit être autorisé par le pare-feu.
- Les plages d’adresses IP et balises de service Azure pour le cloud public doivent être définies conformément aux directives décrites dans : https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>Clients clients Teams pris en charge

La fonctionnalité SBA est prise en charge sur les clients Microsoft Teams suivants : 

- Microsoft Teams Windows bureau 

- Microsoft Teams macOS 

## <a name="how-it-works"></a>Mode de fonctionnement

En cas de panne d’Internet, Teams client doit basculer automatiquement vers le SBA et les appels en cours doivent continuer sans interruptions. Aucune action n’est requise de la part de l’utilisateur. Dès que le client Teams détecte que vous avez accès à Internet et que tous les appels sortants sont terminés, le client revient en mode d’utilisation normal et se connecte à d’Teams services. Le SBA charge les enregistrements de données d’appel collectés dans le cloud et l’historique des appels est mis à jour de telle sorte que ces informations soient disponibles pour révision par l’administrateur client. 

Lorsque le Microsoft Teams client est en mode hors connexion, la fonctionnalité d’appel suivante est disponible : 

- Passer des appels PSTN via SBA/SBC local avec les médias qui parsèment le SBC.

- Réception d’appels PSTN via SBA/SBC local, avec trafic de médias par le SBC. 

- Appels PSTN en attente et reprise.

## <a name="configuration"></a>Configuration

Pour que la fonctionnalité SBA fonctionne, le client Teams doit connaître les SBA disponibles sur chaque site de filiale et les SBA affectés aux utilisateurs de ce site. Les étapes de configuration sont les suivantes :

1. Créez les SBA.
2. Créez la stratégie Teams de capacité d’utilisation des branches.
3. Attribuez la stratégie aux utilisateurs.
4. Enregistrez une application pour SBA auprès de Azure Active Directory.

Toute la configuration est effectuée à l’aide Skype Entreprise cmdlets PowerShell online. (Le Centre Teams d’administration ne prend pas encore en charge la fonctionnalité SBA de routage direct.) 

(Pour plus d’informations sur la configuration du SBC, avec des liens vers la documentation du fournisseur SBC, consultez la configuration du contrôleur de session en bordure à la fin de cet article.)

### <a name="create-the-sbas"></a>Créer les SBA

Pour créer les SBA, vous devez utiliser l'New-CsTeamsSurvivableBranchAppliance cmdlet. Cette cmdlet a les paramètres suivants :

| Paramètre| Description |
| :------------|:-------|
| Identity  | Identité du SBA  |
| Fqdn | FQDN de l’ABA |
| Site | Site TenantNetworkSite où se trouve le SBA |
| Description | Mise en forme gratuite du texte |
|||

Par exemple :

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Créer la stratégie Teams d’accessibilité des branches 

Pour créer une stratégie, vous devez utiliser l'New-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Cette cmdlet possède les paramètres suivants. Notez que la stratégie peut contenir un ou plusieurs SBA.

| Paramètre| Description |
| :------------|:-------|
| Identity | L’identité de la stratégie |
| BranchApplianceFqdns  | FQDN des SBA dans le site |
||

Par exemple :

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Vous pouvez ajouter ou supprimer des SBE d’une stratégie à l’aide de Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Par exemple : 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Affecter une stratégie à un utilisateur

Pour affecter la stratégie à des utilisateurs individuels, vous devez utiliser l'Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Cette cmdlet a les paramètres suivants :

| Paramètre| Description |
| :------------|:-------|
| Identity | Identité de l’utilisateur |
| PolicyName | L’identité de la stratégie |
||

Par exemple :

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Vous pouvez supprimer une stratégie d’un utilisateur en accordant la stratégie $Null,comme illustré dans l’exemple suivant :

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Enregistrer une application pour SBA auprès de Azure Active Directory

Pour permettre à différents SBA utilisés au sein de votre client de lire les données requises à partir de Microsoft 365, vous devez inscrire une application pour le SBA auprès de Azure Active Directory. 

Pour plus d’informations sur l’inscription des applications, voir les informations suivantes :

- [Développez des applications métier pour Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Enregistrez une application auprès du Plateforme d'identités Microsoft.](/azure/active-directory/develop/quickstart-register-app)  

Vous ne devez inscrire qu’une seule application pour être utilisé par tous les SBE de votre client. 

Pour l’inscription SBA, les valeurs suivantes doivent être créées par l’inscription : 

- ID d’application (client) 
- Client secret 

Pour l’application SBA, gardez les choses suivantes à l’esprit : 

- Le nom peut être ce que vous décidez.  
- Types de comptes pris en charge = Compte dans cet annuaire de l’organisation uniquement. 
- Uri de redirection web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Jetons d’octroi implicites = jetons Access et ID. 
- Autorisations de l’API = Skype et Teams’accès de l’administrateur client ->'application - > application_access_custom_sba_appliance.
- Secret client : vous pouvez utiliser n’importe quelle description et expiration. 
- N’oubliez pas de copier le secret client immédiatement après l’avoir créé. 
- L’ID d’application (client) s’affiche dans l’onglet Vue d’ensemble.

Ensuite, suivez ces étapes :

1. Enregistrez l’application.
2. Définissez les jetons d’octroi implicites.
3. Définissez les autorisations de l’API.
4. Créez le secret client.


## <a name="session-border-controller-configuration"></a>Configuration du contrôleur de session Border 

Pour obtenir une aide étape par étape sur la configuration de votre contrôleur de session border avec l’appliance de branche utilisable pour la survie, consultez la documentation fournie par votre fournisseur SBC : 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Ruban](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Signaler des problèmes

Signalez les problèmes à l’organisation de support de votre fournisseur SBC. Lorsque vous signalez le problème, indiquez que vous avez configuré une appliance de branche utilisable en survivable.

## <a name="known-issues"></a>Problèmes connus

- L’ajout de nouveaux équipements de branches survivables peut prendre un certain temps avant de pouvoir les utiliser dans les stratégies d’appliance de branche survivable.

- Lorsque vous affectez une stratégie d’équipement de branche survivable à un utilisateur, l’utilisation de SBA dans la sortie de Get-CsOnlineUser peut prendre un certain temps. 

- La recherche inversée de nombre par rapport Azure AD Contacts n’est pas effectuée. 

- Le SBA ne prend pas en charge les paramètres de forwardage d’appel. 

- La prise en charge d’un appel d’urgence vers un numéro de secours configuré pour les appels d’urgence dynamiques (E911) n’est pas prise en charge.
