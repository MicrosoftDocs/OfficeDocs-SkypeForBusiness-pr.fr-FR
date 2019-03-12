---
title: Quels sont les standards automatiques du système téléphonique?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Découvrez quelles sont les standards automatiques de système téléphonique (PBX en nuage) et comment les utiliser.
ms.openlocfilehash: 14499789287e23767429392f0c21b66d56372ac0
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542278"
---
# <a name="what-are-phone-system-auto-attendants"></a>Quels sont les standards automatiques du système téléphonique?

Système téléphonique dans Office 365 fournit des standards automatiques, qui peuvent être utilisés pour permettre aux externe et internes appelants déplacement dans un système de menus pour localiser et placer ou transférer des appels vers les utilisateurs de la société ou département au sein de votre organisation.
  
Un standard automatique est une série d’invites vocales ou les fichiers audio que les appelants entendront au lieu d’un opérateur humain quand ils appellent une organisation. Personnes d’appeler un numéro associé à un standard automatique, leur choix permettre rediriger l’appel à un utilisateur ou rechercher une personne dans votre organisation, puis connectez-vous à cet utilisateur. Ils peuvent express de leur choix et interagir avec le système de menus à l’aide d’un pavé numérique du téléphone (DTMF) ou la reconnaissance vocale.
  
Pour configurer un standard automatique pour le système téléphonique dans Office 365, accédez à [configurer un standard automatique de système téléphonique](create-a-phone-system-auto-attendant.md).
  
Un standard automatique de système téléphonique comprend les fonctionnalités suivantes :
  
- Il propose des messages d'accueil spécifiques de l'entreprise ou à vocation informative.
- Il propose des menus d'entreprise personnalisés. Vous pouvez personnaliser ces menus afin de disposer de plusieurs niveaux.
- Il fournit la recherche dans l’annuaire qui permet à des personnes appellent recherche dans le répertoire de l’organisation pour un nom.
- Il permet à une personne qui appelle l’appel ou laisser un message d’une personne dans votre organisation.

> [!NOTE]
> Cet article s’applique à Microsoft Teams et Skype pour Business Online.

## <a name="getting-started"></a>Mise en route

Avant de commencer à utiliser les standards automatiques, il est impératif de noter les points suivants :
  
- Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5. Le nombre de licences utilisateur **Système téléphonique** qui sont affectés des impacts sur le numéro de service des numéros est disponible pour être utilisés pour les standards automatiques. Le nombre de standards automatiques que vous avez dépend des licences numéros **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation. Pour plus d’informations sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne avec une licence de **Système téléphonique** , vous devez les activer pour Enterprise Voice ou de leur attribuer des Plans de l’appel. Consultez les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour obtenir et utiliser des numéros gratuits service pour vos standards automatiques, vous devez configurer les crédits de Communications. Pour ce faire, consultez la rubrique [Quelles sont les Communications crédits ?](what-are-communications-credits.md) et [configurer les Communications crédits pour votre organisation](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des standards automatiques. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés.
- Un standard automatique est nécessaire d’avoir un compte de ressource. Pour plus d’informations sur les comptes de ressources, voir [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) .
- Un système de standard automatique terminée implique généralement plusieurs standards automatiques et nécessitent qu’un numéro de téléphone affecté unique pour le niveau supérieur ou entrée automatique standard. Autres standards automatiques ou les files d’attente des appels dans le système doivent uniquement un numéro de téléphone si vous souhaitez fournir plusieurs points d’entrée dans le système.
- Il est possible d’appliquer plusieurs numéros de téléphone à un standard automatique de l’association de plusieurs numéros de téléphone pour le compte de la ressource du standard automatique.
  
## <a name="feature-overview"></a>Présentation de la fonctionnalité

### <a name="dial-by-name"></a>Numérotation par nom

Numérotation par nom est une fonctionnalité d’un standard automatique est également appelé recherche dans l’annuaire. Il permet des personnes qui appeler votre standard automatique afin d’utiliser la voix (reconnaissance vocale) ou leurs réponses du pavé numérique (DTMF) téléphone pour entrer un nom complet ou partiel à rechercher l’annuaire d’entreprise, recherchez la personne et puis transférer l’appel correspondantes. Utilisateurs qui ont trouve et atteinte à l’aide de la numérotation par nom **ne sont pas obligatoires pour avoir un numéro de téléphone ou leur appel Plans attribuez, mais ils doivent disposer d’une licence de système téléphonique**. Numérotation par nom pourront même rechercher et transférer des appels aux utilisateurs de Microsoft Teams qui sont hébergées dans plusieurs pays ou régions pour les organisations multinationale.

### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Il n’existe aucune limite la taille d’Active Directory pour lesquels la numérotation par nom est pris en charge lors de l’utilisation du clavier du téléphone pour rechercher les noms complet ou partiel (FirstName + LastName, également LastName et FirstName). Toutefois, la taille de liste maximale pour le nom qu’un standard automatique unique peut prendre en charge à l’aide de la reconnaissance de nom avec la voix est 80 000 utilisateurs.
  
|Type d'entrée|Format de recherche|Nombre maximal d'utilisateurs dans une organisation|
|:-----|:-----|:-----|
|DTMF (entrée de clavier de téléphone) |Partiel  <br/> Prénom + nom  <br/> Nom + prénom |Aucune limite stricte  |
|Voix (entrée vocale) |Prénom  <br/> LastName  <br/> Prénom + nom  <br/> Nom + prénom  |80 000 utilisateurs |

> [!NOTE]
> Si vous utilisez la numérotation par un nom avec la voix de reconnaissance, mais Active Directory votre organisation est supérieure à 80 000 utilisateurs et vous n’avez pas limité à l’étendue de numérotation par un nom à l’aide de la fonctionnalité d’étendue de numérotation, numérotation par nom continuent de fonctionner pour vos interlocuteurs à l’aide d’un clavier de téléphone , et les entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Personnes appelant peuvent utiliser à distance par un nom d’atteindre des utilisateurs en spécifiant soit le nom complet ou partiel de la personne qu’il tente d’accéder. La bonne chose est qu’il existe différents formats qui peuvent être utilisés lorsque le nom est entré.

Lorsqu'ils recherchent dans l'annuaire de votre organisation, les utilisateurs peuvent utiliser la touche 0 (zéro) pour indiquer un espace entre le prénom et le nom ou vice versa. Lorsqu'ils saisissent le nom, ils seront invités à terminer leur entrée de clavier par la touche # (dièse). Par exemple : « Après avoir saisi le nom de la personne que vous voulez joindre, appuyez sur #. » Si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les employés peuvent rechercher des noms dans votre organisation à l'aide des formats de recherche suivants sur leur clavier téléphonique :
  
|Format de nom|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet  |Amos0Marble# |Amos Marble |
|Nom + prénom |Complet |Marble0Amos#  |Amos Marble |
|Prénom  |Complet   |Amos#   |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|LastName |Complet |Marble#  |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Mary Marble |
|Prénom ou nom |Partiel |Mar# |Appuyez sur 1 pour Mary Marble  <br/> Appuyez sur 2 pour Mary Jones  <br/> Appuyez sur 3 pour Amos Marcus |
|Prénom + nom |Partiel |Mar0Amos# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Nom + prénom |Partiel |Mar0Am# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |

Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne devront utiliser la touche dièse (#), tandis que la touche zéro (0) est utilisée pour un espace de noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|Caractère spécial du clavier téléphonique|Signification|
|:-----|:-----|
|# (touche dièse) |Caractère de fin de saisie d'un nom |
|0 (zéro) |Espace entre les noms |
|* (touche étoile)  |Répétition de la liste de correspondances de noms |

### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Personnes peuvent rechercher d’autres utilisateurs dans leur organisation à l’aide de la voix (reconnaissance vocale). Ils peuvent également joindre tout le monde dans Active Directory de l’entreprise en indiquant le nom de la personne, qu’ils vous recherchez. À l’aide d’entrées vocales peut reconnaître les noms dans différents formats, y compris FirstName, LastName, FirstName LastName, ou LastName + FirstName.
  
Lorsque vous activez la reconnaissance vocale pour un standard automatique, entrée de clavier de téléphone (DTMF) n’est pas désactivée, les deux types d’entrée peuvent être utilisée. Entrée clavier de téléphone ne peut pas être désactivée et peut être utilisée à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
Comme avec l'entrée de clavier téléphonique, si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les appelants peuvent prononcer les noms dans les formats suivants :
  
|Nom de la reconnaissance vocale|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet |Amos Marble |Amos Marble |
|Nom + prénom |Complet  |Marble Amos |Amos Marble |
|Prénom |Complet |Amos |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones |
|LastName |Complet |Marble |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble |

> [!NOTE]
> Cela peut prendre jusqu'à 36 heures pour un nouvel utilisateur à leur nom apparaît dans le répertoire de numérotation par un nom pour la reconnaissance vocale.
  
### <a name="language-support"></a>Prise en charge des langues

Les langues suivantes sont disponibles pour la synthèse vocale :
  
||||
|:-----|:-----|:-----|
|Arabe (EG)  |Anglais (NZ)  |Coréen (KO)  |
|Chinois (HK)  |Anglais (Royaume-Uni) |Norvégien (NO)  |
|Chinois (TW) |Anglais (É.U.) |Polonais (PL)  |
|Chinois (ZH) |Finnois (FI) |Portugais (BR) |
|Danois (DA)  |Français (CA)  |Portugais (PT) |
|Néerlandais (NL)   |Français (FR)  |Russe (RU) |
|Anglais (AU)  |Allemand (DE) |Espagnol (ES)  |
|Anglais (CA)  |Italien (IT) |Espagnol (MX)|
|Anglais (IN)  |Japonais (JP) |Suédois (SV)|

La reconnaissance vocale pour les standards automatiques est disponible pour les langues suivantes :
  
|||
|:-----|:-----|
|Chinois (ZH)  |Français (FR)  |
|Anglais (AU)  |Allemand (DE)  |
|Anglais (CA)  |Italien (IT)  |
|Anglais (IN)  |Japonais (JP)  |
|Anglais (Royaume-Uni)  |Portugais (BR)  |
|Anglais (É.U.)  |Espagnol (ES)  |
|Français (CA)   |Espagnol (MX)  |

Les commandes vocales suivantes sont disponibles dans les quatorze (14) langues prises en charge par la reconnaissance vocale :
  
|Commande vocale|Signification|
|:-----|:-----|
|Oui |Oui correspond à appuyer sur 1 pour indiquer Oui. |
|Non |Non correspond à appuyer sur 2 pour indiquer Non. |
|Répéter |Répète la liste des options - correspond à appuyer sur * pour répéter la liste des options. |
|Opérateur |Contacter un opérateur - correspond à appuyer sur 0 pour « Opérateur ». |
|Menu principal  |Dirige l'appelant vers le menu principal du standard automatique. |
|Zéro |Correspond à appuyer sur 0 (par défaut, identique à « Opérateur »).|
|Un |Correspond à appuyer sur 1. |
|Deux |Correspond à appuyer sur 2. |
|Trois|Correspond à appuyer sur 3.|
|Quatre |Correspond à appuyer sur 4. |
|Cinq |Correspond à appuyer sur 5. |
|Six  |Correspond à appuyer sur 6. |
|Sept |Correspond à appuyer sur 7.|
|Huit |Correspond à appuyer sur 8.|
|Neuf  |Correspond à appuyer sur 9.|

### <a name="using-the-operator-option"></a>Utilisation de l'option opérateur

L'utilisation de l'opérateur d'un standard automatique est un paramètre facultatif qui permet à l'appelant de contacter une personne.
  
La touche 0 et la commande vocale « Opérateur » (dans toutes les langues prises en charge par la reconnaissance vocale) sont affectées à l'opérateur par défaut.
  
> [!NOTE]
> Vous pouvez définir le bouton qui est ensuite à une autre clé pour l' **opérateur** à l’aide des **Options de Menu**.
  
Vous pouvez définir l'opérateur comme suit :
  
- Un utilisateur de Microsoft Teams qui dispose d’un **Système téléphonique** de licence qui est prenant en charge Enterprise Voice ou a appelant Plans assigné. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.

    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne peut pas être utilisé comme un opérateur.
  
- Un autre standard automatique configuré dans votre organisation
- Une file d'attente existante configurée dans votre organisation. Pour plus d’informations sur les files d’attente des appels, consultez [créer une file d’attente des appels système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Heures d'ouverture et traitement des appels

Les heures d'ouverture sont définies sur chaque standard automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures de bureau peut être définies avec sauts de temps au cours de la journée et toutes les heures qui ne sont pas définies comme heures ouvrées sont considérés comme étant en continu. Vous pouvez définir différentes options de gestion des appels entrantes et le message d’accueil différents (qui est facultatives) et à la fois peuvent être définies pour les heures de bureau et en continu.
  
Chaque standard automatique comprend des options de gestion des appels qui peuvent être définies :
  
- Vous pouvez définir la déconnexion de l'appel juste après le message d'accueil.
- Vous pouvez également :
  - Rediriger l’appel vers un utilisateur de Microsoft Teams ayant une licence de **Système téléphonique** prenant en charge Enterprise Voice ou a appelant Plans assigné. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.

    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.
  
  - Rediriger l’appel vers une file d’attente de l’appel. Pour plus d’informations sur les files d’attente des appels, consultez [créer une file d’attente des appels système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Rediriger l’appel vers un autre standard automatique que vous avez configurées.
- Créer des options de menu et activer une invite de menu pour l'appelant. Par exemple : « Appuyez sur 1 pour contacter le département des ventes, appuyez sur 2 pour contacter le département des services. Pour contacter l'opérateur, appuyez sur 0 à tout moment. »

### <a name="menu-options"></a>Options de menu

Standards automatiques de système téléphonique permettent de créer des invites de menu (« appuyez sur 1 pour la vente, appuyez sur 2 pour les Services ») et définir les options de menu pour acheminer les appels en fonction de ce que l’utilisateur sélectionne. La configuration des options de menu d'un standard automatique permet à une organisation de fournir une assistance interactive pour orienter rapidement l'appelant vers sa destination, sans recourir à un opérateur humain pour la gestion des appels entrants. Invites peuvent être créés à l’aide de la synthèse vocale (invites généré par le système) ou en téléchargeant un fichier audio qui a été enregistré. La reconnaissance vocale utilise des commandes vocales pour naviguer en mode mains libres, mais les appelants peuvent également utiliser leur clavier téléphonique pour parcourir les menus.
  
Touches 0 à 9 peuvent être assignés aux **Options de Menu** dans un standard automatique à l’aide de la Skype entreprise centre d’administration. Plusieurs ensembles d'options de menu peuvent être créés pour les heures d'ouverture et de fermeture et vous pouvez activer ou désactiver la fonction Numérotation par nom dans les **Options de menus**. Les touches peuvent être mappées pour transférer les appels vers :
  
- Un opérateur, mappé vers la touche 0 par défaut. Toutefois, il peut être réaffecté à n’importe quelle autre touche ou supprimé du menu.
- Une file d’attente de l’appel.
- Un autre standard automatique. Menus à plusieurs niveaux peuvent être configurées en pointant une **Option de Menu** dans le standard automatique d’un à un autre standard automatique avec son propre ensemble d’Options de Menu, qui est appelée un standard automatique « imbriqués ».
- Un utilisateur de Microsoft Teams qui dispose d’un **Système téléphonique** de licence qui est prenant en charge Enterprise Voice ou a appelant Plans assigné. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.

    > [!NOTE]
    > Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne peut pas être utilisé dans les **Options de Menu**.
  
Le nom de chaque option de menu devient un mot clé de la reconnaissance vocale si la reconnaissance vocale a été activée. Par exemple, les appelants peuvent prononcer « One » pour sélectionner l’option de menu mappée à la clé 1, ou ils peuvent simplement dire « Sales » pour sélectionner l’option de menu même nommée « Sales ».
  
Pour configurer un standard automatique et les options de menu, consultez [configurer un standard automatique de système téléphonique](create-a-phone-system-auto-attendant.md).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Obtention de numéros de service pour un standard automatique

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Skype pour le centre d’administration Business** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - numéro gratuit **. Pour obtenir vos numéros de service, voir les [numéros de téléphone de service de mise en route pour Skype pour les professionnels et les équipes Microsoft](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) ou, si vous souhaitez transférer et le numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Skype entreprise centre d’administration pour obtenir les numéros de service. Accédez [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modifier l'ID de l’appelant de l’utilisateur pour le transformer en numéro de téléphone de la file d’attente

Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.
  
Pour ce faire, exécutez :
  
``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Ensuite, appliquez la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** . Pour ce faire, exécutez :
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation, [l’ID d’appelant utilisation dans votre organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="related-topics"></a>Rubriques connexes

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemple de petite entreprise - configurer un standard automatique](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)
