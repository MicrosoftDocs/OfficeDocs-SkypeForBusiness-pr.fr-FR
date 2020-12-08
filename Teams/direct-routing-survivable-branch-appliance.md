---
title: Service de routage direct SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: En savoir plus sur le routage direct, tel que la configuration, les décisions de déploiement principales nécessaires et les considérations en matière de routage vocal.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588598"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Appareil de branchement survivant (SBA) pour le routage direct-Aperçu public


> [!NOTE]
> Il s’agit d’une version bêta publique.

Occasionnellement, un site client utilisant le routage direct pour se connecter au système Microsoft Phone peut rencontrer une panne Internet.

Supposez que le site du client (appelé succursale) ne peut pas se connecter à Microsoft Cloud par le biais du routage direct. Toutefois, l’intranet au sein de la succursale reste entièrement fonctionnel et les utilisateurs peuvent se connecter au contrôleur de bordure de session (SBC) fournissant une connectivité PSTN.

Cet article décrit comment utiliser une application de branchement Survivable (SBA) pour permettre au système Microsoft Phone de continuer à passer et à recevoir des appels de réseau téléphonique commuté (PSTN) en cas de panne.

## <a name="prerequisites"></a>Conditions préalables

Le code de l’erreur SBA est fourni par Microsoft aux fournisseurs de SBC qui incorporent ensuite le code dans le microprogramme de leur SBCs. 

Pour obtenir le dernier microprogramme de contrôleur de bordure de session avec l’appareil de branchement Survivable intégré, contactez votre fournisseur de SBC. Par ailleurs, les informations suivantes sont nécessaires :

- L’élément SBC doit être configuré pour la dérivation de média pour s’assurer que le client Microsoft teams dans le site de succursale peut mettre le contenu multimédia en flux direct avec l’SBC. 

- TLS 1.2 doit être activé sur le système d’exploitation de l’ordinateur virtuel SBA.

## <a name="supported-teams-clients"></a>Clients équipes pris en charge

La fonction SBA est prise en charge sur les clients Microsoft teams suivants : 

- Bureau Microsoft teams 

- Bureau Microsoft teams macOS 

## <a name="how-it-works"></a>Mode de fonctionnement

Au cours d’une panne d’Internet, le client teams doit basculer vers le SBA automatiquement et les appels en cours continuent sans interruption. Aucune action n’est requise de la part de l’utilisateur. Dès que le client teams a détecté que la connexion à Internet fonctionne et que tous les appels sortants sont terminés, le client revient au mode de fonctionnement normal et se connecte à d’autres services Teams. Le SBA télécharge les enregistrements de données d’appel collectés vers le Cloud et l’historique des appels sera mis à jour de manière à ce que ces informations puissent être consultées par l’administrateur client. 

Lorsque le client Microsoft teams est en mode hors connexion, les fonctionnalités d’appel suivantes sont disponibles : 

- Appels RTC par le biais d’un réseau local SBA/SBC avec les contenus multimédias acheminés par l’intermédiaire de l’SBC.

- Réception d’appels RTC par le biais d’un réseau local SBA/SBC avec média passant par le SBC. 

- Mise en attente et reprise d’appels RTC.

## <a name="configuration"></a>Configuration

Pour que la fonctionnalité SBA fonctionne, le client teams doit savoir quels SBAs sont disponibles dans chaque site de filiale et quels SBAs sont attribués aux utilisateurs de ce site. Les étapes de configuration sont les suivantes :

1. Créez l’SBAs.
2. Créer la stratégie de survie de la succursale Teams.
3. Affectez la stratégie aux utilisateurs.
4. Enregistrez une application pour le SBA avec Azure Active Directory.

La configuration est terminée en utilisant les cmdlets PowerShell de Skype entreprise online. (Le centre d’administration Teams ne prend pas encore en charge la fonctionnalité de routage directe SBA.) 

(Pour plus d’informations sur la configuration de l’SBC, avec des liens vers la documentation du fournisseur SBC, voir Configuration de contrôleur de bordure de session à la fin de cet article.)

### <a name="create-the-sbas"></a>Créer le SBAs

Pour créer le SBAs, vous devez utiliser l’applet de passe New-CsTeamsSurvivableBranchAppliance. Cette applet de commande a les paramètres suivants :

| Paramètre| Description |
| :------------|:-------|
| Identity  | Nom de domaine complet du SBA  |
| Fqdn | Nom de domaine complet du SBA |
| Site | Le TenantNetworkSite dans lequel se trouve l’SBA |
| Description | Mettre en forme du texte libre |
|||

Par exemple :

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Créer la stratégie de survie de la succursale teams 

Pour créer une stratégie, vous devez utiliser l’applet de New-CsTeamsSurvivableBranchAppliancePolicy. Ce cmdlet a les paramètres suivants. Notez que la stratégie peut contenir au moins un SBAs.

| Paramètre| Description |
| :------------|:-------|
| Identity | Identité de la stratégie. |
| BranchApplianceFqdns  | Nom de domaine complet (FQDN) du site |
||

Par exemple :

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

Vous pouvez ajouter ou supprimer SBAs d’une stratégie à l’aide de l’applet de Set-CsTeamsSurvivableBranchAppliancePolicy. Par exemple : 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Attribuer une stratégie à un utilisateur

Pour affecter la stratégie à des utilisateurs individuels, vous devez utiliser l’applet de Grant-CsTeamsSurvivableBranchAppliancePolicy. Ce cmdlet comporte les paramètres suivants :

| Paramètre| Description |
| :------------|:-------|
| Identity | Identité de l’utilisateur. |
| PolicyName | Identité de la stratégie. |
||

Par exemple :

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Vous pouvez supprimer une stratégie d’un utilisateur en autorisant la stratégie de $Null comme le montre l’exemple suivant :

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Inscrire une application pour l’SBA auprès d’Azure Active Directory

Pour permettre à différentes SBAs d’être utilisés dans votre client pour lire les données requises de Microsoft 365, vous devez inscrire une application pour l’SBA auprès d’Azure Active Directory. 

Pour plus d’informations sur l’inscription des applications, voir les rubriques suivantes :

- [Développer des applications métier pour Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Enregistrez une application à l’aide de la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).  

Il vous suffit d’inscrire une seule application pour pouvoir l’utiliser dans tous les SBAs de votre client. 

Pour l’inscription SBA, vous avez besoin des valeurs suivantes créées par l’inscription : 

- ID de l’application (client) 
- Clé secrète client 

Pour l’application SBA, gardez les points suivants à l’esprit : 

- Il peut s’agir du nom de votre choix.  
- Types de comptes pris en charge = compte uniquement dans cet annuaire d’organisation. 
- URI de redirection Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Jetons d’attribution implicite = jetons d’accès et jetons d’ID. 
- Autorisations d’API = autorisation d’accès de l’administrateur client de Skype et teams-> > application_access_custom_sba_appliance.
- Clé secrète client : vous pouvez utiliser n’importe quelle description et votre date d’expiration. 
- N’oubliez pas de copier la clé secrète du client immédiatement après l’avoir créée. 
- L’ID de l’application (client) est affiché dans l’onglet vue d’ensemble.

Procédez comme suit :

1. Enregistrez l’application.
2. Définissez les jetons d’attribution implicite.
3. Définissez les autorisations d’API.
4. Créez la clé secrète client.


## <a name="session-border-controller-configuration"></a>Configuration du contrôleur de bordure de session 

Pour obtenir des instructions détaillées sur la configuration de votre contrôleur de bordure de session avec l’appareil de branche Survivable intégré, voir la documentation fournie par votre fournisseur de SBC : 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [»](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-systèmes](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Signalement de problèmes

Signaler les problèmes à l’organisation du support technique de votre fournisseur de SBC. Lorsque vous signalez le problème, indiquez que vous disposez d’une unité de branchement survivant configurée.

## <a name="known-issues"></a>Problèmes connus

- Lorsque vous ajoutez de nouvelles applications de succursales survivant, il est possible que vous deviez prendre un peu de temps pour pouvoir les utiliser dans les stratégies de l’appareil de branchement Survivables.

- Lorsque vous attribuez une stratégie d’appareil de succursale Survivable à un utilisateur, l’affichage de la stratégie Get-CsOnlineUser peut prendre un peu de temps. 

- La recherche de numéro inversée des contacts Azure AD n’est pas effectuée. 

- Le SBA ne prend pas en charge les paramètres de transfert d’appel. 

- Les appels d’urgence vers un numéro d’urgence configuré pour les appels d’urgence dynamiques (E911) ne sont pas pris en charge.

- La sortie de Get-CsOnlineUser montre TeamsBranchSurvivabilityPolicy.
