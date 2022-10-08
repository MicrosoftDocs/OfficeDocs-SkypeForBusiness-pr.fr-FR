---
title: SBA de routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur le routage direct, comme la configuration, les décisions de déploiement de base nécessaires et les considérations relatives au routage vocal.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 976c73aebe698152c4824e3eaedfcc19a13ae525
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138487"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Survivable Branch Appliance (SBA) pour le routage direct


Parfois, un site client utilisant le routage direct pour se connecter à Microsoft Phone System peut rencontrer une panne Internet.

Supposons que le site client, appelé branche, ne peut pas se connecter temporairement au cloud Microsoft via le routage direct. Toutefois, l’intranet à l’intérieur de la branche est toujours entièrement fonctionnel et les utilisateurs peuvent se connecter au contrôleur de bordure de session (SBC) qui fournit une connectivité RTC.

Cet article explique comment utiliser survivable Branch Appliance (SBA) pour permettre à Microsoft Phone System de continuer à passer et à recevoir des appels rtc (RTC) en cas de panne.

## <a name="prerequisites"></a>Conditions préalables

SBA est un code distribuable fourni par Microsoft aux fournisseurs SBC qui incorporent ensuite du code dans leur microprogramme ou le distribuent séparément pour que SBA s’exécute sur une machine virtuelle ou un matériel distinct. 

Pour obtenir le dernier microprogramme du contrôleur de bordure de session avec l’appliance survivable Branch Appliance incorporée, contactez votre fournisseur SBC. En outre, les éléments suivants sont requis :

- Le SBC doit être configuré pour media bypass afin de s’assurer que le client Microsoft Teams dans le site de la branche peut avoir des médias qui circulent directement avec le SBC. 

- TLS1.2 doit être activé sur le système d’exploitation de machine virtuelle SBA.
- Les ports 3443, 4444 et 8443 sont utilisés par Microsoft SBA Server pour communiquer avec le client Teams et doivent être autorisés sur le pare-feu. 
- Le port 5061 (ou celui configuré sur le SBC) est utilisé par Microsoft SBA Server pour communiquer avec le SBC et doit être autorisé sur le pare-feu. 
- Le port UDP 123 est utilisé par Microsoft SBA Server pour communiquer avec le serveur NTP et doit être autorisé sur le pare-feu.
- Le port 443 est utilisé par Microsoft SBA Server pour communiquer avec Microsoft 365 et doit être autorisé sur le pare-feu.
- Les plages d’adresses IP Azure et les balises de service pour le cloud public doivent être définies conformément aux instructions décrites dans : https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>Clients Teams pris en charge

La fonctionnalité SBA est prise en charge sur les clients Microsoft Teams suivants : 

- Bureau Windows Microsoft Teams 

- Bureau macOS Microsoft Teams
- Teams pour mobile 
- Téléphones Teams

## <a name="how-it-works"></a>Mode de fonctionnement

En cas de panne d’Internet, le client Teams doit basculer automatiquement vers l’accès SBA, et les appels en cours doivent se poursuivre sans interruption. Aucune action n’est requise de la part de l’utilisateur. Dès que le client Teams détecte qu’Internet est activé et que tous les appels sortants sont terminés, le client revient en mode d’opération normal et se connecte à d’autres services Teams. L’administrateur SBA charge les enregistrements de données d’appel collectés dans le cloud et l’historique des appels est mis à jour afin que ces informations soient disponibles pour révision par l’administrateur client. 

Lorsque le client Microsoft Teams est en mode hors connexion, les fonctionnalités liées à l’appel suivantes sont disponibles : 

- Effectuer des appels RTC via SBA/SBC local avec un média qui transite par le SBC.

- Réception d’appels RTC via SBA/SBC local avec un média transitant par le SBC. 

- Conserver et reprendre les appels RTC.

## <a name="configuration"></a>Configuration

Pour que la fonctionnalité SBA fonctionne, le client Teams doit savoir quels SBA sont disponibles dans chaque site de branche et quels SBA sont affectés aux utilisateurs de ce site. Les étapes de configuration sont les suivantes :

1. Créez les SBA.
2. Créez la stratégie de survivabilité de la branche Teams.
3. Affectez la stratégie aux utilisateurs.
4. Inscrivez une application pour l’application SBA auprès d’Azure Active Directory.

Toute la configuration est effectuée à l’aide Skype Entreprise applets de commande PowerShell en ligne. (Le Centre d’administration Teams ne prend pas encore en charge la fonctionnalité SBA de routage direct.) 

(Pour plus d’informations sur la configuration du SBC, avec des liens vers la documentation du fournisseur SBC, consultez la configuration du contrôleur de bordure de session à la fin de cet article.)

### <a name="create-the-sbas"></a>Créer les SBA

Pour créer les SBA, vous allez utiliser l’applet de commande New-CsTeamsSurvivableBranchAppliance. Cette applet de commande a les paramètres suivants :

| Paramètre| Description |
| :------------|:-------|
| Identity  | Identité de l’administrateur de base de données  |
| Fqdn | Nom de domaine complet du SBA |
| Site | TenantNetworkSite où se trouve l’administrateur SBA |
| Description | Texte au format libre |
|||

Par exemple :

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Créer la stratégie de survivabilité de Teams Branch 

Pour créer une stratégie, vous utilisez l’applet de commande New-CsTeamsSurvivableBranchAppliancePolicy. Cette applet de commande a les paramètres suivants. Notez que la stratégie peut contenir un ou plusieurs contrats SBA.

| Paramètre| Description |
| :------------|:-------|
| Identity | Identité de la stratégie |
| BranchApplianceFqdns  | Nom de domaine complet des SBA dans le site |
||

Par exemple :

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Vous pouvez ajouter ou supprimer des SDA d’une stratégie à l’aide de l’applet de commande Set-CsTeamsSurvivableBranchAppliancePolicy. Par exemple : 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Affecter une stratégie à un utilisateur

Pour affecter la stratégie à des utilisateurs individuels, vous allez utiliser l’applet de commande Grant-CsTeamsSurvivableBranchAppliancePolicy. Cette applet de commande a les paramètres suivants :

| Paramètre| Description |
| :------------|:-------|
| Identity | Identité de l’utilisateur |
| PolicyName | Identité de la stratégie |
||

Par exemple :

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Vous pouvez supprimer une stratégie d’un utilisateur en lui accordant la stratégie $Null comme indiqué dans l’exemple suivant :

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Inscrire une application pour SBA auprès d’Azure Active Directory

Pour permettre à différents SBA utilisés au sein de votre locataire de lire les données requises à partir de Microsoft 365, vous devez inscrire une application pour l’application SBA auprès d’Azure Active Directory. 

Pour plus d’informations sur l’inscription d’application, consultez les rubriques suivantes :

- [Développer des applications métier pour Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Inscrivez une application auprès du Plateforme d'identités Microsoft](/azure/active-directory/develop/quickstart-register-app).  

Vous n’avez besoin d’inscrire qu’une seule application pour qu’elle soit utilisée par toutes les autorités de certification de votre locataire. 

Pour l’inscription SBA, vous avez besoin des valeurs suivantes créées par l’inscription : 

- ID d’application (client) 
- Clé secrète client 

Pour l’application SBA, gardez à l’esprit les éléments suivants : 

- Le nom peut être ce que vous décidez.  
- Types de comptes pris en charge = Compte dans cet annuaire organisationnel uniquement. 
- Uri de redirection web = https://login.microsoftonline.com/common/oauth2/nativeclient.
- Jetons d’octroi implicite = Jetons d’accès et jetons d’ID. 
- Autorisations d’API = Locataire Skype et Teams Administration Access -> Autorisations d’application -> application_access_custom_sba_appliance.
- Clé secrète client : vous pouvez utiliser n’importe quelle description et expiration. 
- N’oubliez pas de copier la clé secrète client immédiatement après sa création. 
- L’ID d’application (client) s’affiche sous l’onglet Vue d’ensemble.

Procédez comme suit :

1. Inscrivez l’application.
2. Définissez les jetons d’octroi implicites.
3. Définissez les autorisations d’API.
4. Créez la clé secrète client.


## <a name="session-border-controller-configuration"></a>Configuration du contrôleur de bordure de session 

Pour obtenir des instructions pas à pas sur la configuration de votre contrôleur de frontière de session avec l’appliance survivable Branch appliance incorporée, consultez la documentation fournie par votre fournisseur SBC : 

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [Ruban](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Signaler des problèmes

Signalez les problèmes à l’organisation de support technique de votre fournisseur SBC. Lorsque vous signalez le problème, indiquez que vous disposez d’une appliance Survivable Branch Appliance configurée.

## <a name="known-issues"></a>Problèmes connus

- SBA s’appuyant sur des jetons d’authentification valides pendant 24 heures et renouvelés quotidiennement, SBA peut actuellement prendre en charge les pannes jusqu’à 24 heures à partir de la dernière authentification. Cela signifie que si une panne se produit 20 heures après le dernier renouvellement du jeton d’authentification, SBA sera opérationnel uniquement pendant les 4 heures restantes.

- Lorsque vous ajoutez de nouvelles appliances Survivable Branch Appliances, cela peut prendre un certain temps avant de pouvoir les utiliser dans les stratégies Survivable Branch Appliance.

- Lorsque vous attribuez une stratégie Survivable Branch Appliance à un utilisateur, l’affichage de l’authentification unique dans la sortie de Get-CsOnlineUser peut prendre un certain temps. 

- La recherche de numéros inversés sur les contacts Azure AD n’est pas effectuée. 

- L’administrateur SBA ne prend pas en charge les paramètres de transfert d’appel. 

- L’appel d’urgence à un numéro d’urgence configuré pour les appels d’urgence dynamiques (E911) n’est pas pris en charge.
