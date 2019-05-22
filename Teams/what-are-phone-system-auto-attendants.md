---
title: Que sont les standards automatiques Cloud?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Découvrez les standards automatiques du Cloud et comment les utiliser.
ms.openlocfilehash: ae5d959918240cec63c925eff77653c54294e99c
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2019
ms.locfileid: "34330355"
---
# <a name="what-are-cloud-auto-attendants"></a>Que sont les standards automatiques Cloud?

Le système téléphonique dans Office 365 fournit des standards automatiques qui peuvent être utilisés pour permettre aux appelants externes et internes de se déplacer dans un système de menus afin de localiser et de transférer les appels vers des utilisateurs ou services de la société au sein de votre organisation.
  
Un standard automatique est une série d’invites vocales ou de fichiers audio que les appelants entendent au lieu d’un opérateur humain lorsqu’ils appellent une organisation. Lorsque des personnes appellent un numéro associé à un standard automatique, leurs choix peuvent rediriger l’appel vers un utilisateur ou localiser une personne de votre organisation, puis se connecter à cet utilisateur. Ils peuvent exprimer leurs choix et interagir avec le système de menus à l’aide d’un clavier téléphonique (DTMF) ou d’une reconnaissance vocale.
  
Pour configurer un standard automatique pour le système téléphonique dans Office 365, voir [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).
  
Le standard automatique Cloud offre les fonctionnalités suivantes:
  
- Il propose des messages d'accueil spécifiques de l'entreprise ou à vocation informative.
- Il propose des menus d'entreprise personnalisés. Vous pouvez personnaliser ces menus afin de disposer de plusieurs niveaux.
- Il fournit une recherche dans l’annuaire permettant aux personnes qui rejoignent la recherche d’un nom dans l’annuaire de l’organisation.
- Il permet à une personne qui appelle pour joindre ou laisser un message à une personne de votre organisation.
- Il prend en charge plusieurs langues pour les invites, la conversion de texte par synthèse vocale et la reconnaissance vocale.
- Elle prend en charge la définition des jours fériés et des heures d’activité.
- Il prend en charge le transfert d’appel vers un opérateur, d’autres utilisateurs, des files d’attente d’appels et des standards automatiques.

> [!NOTE]
> Cet article s’applique à Microsoft teams et à Skype entreprise online.

## <a name="getting-started"></a>Prise en main

Avant de commencer à utiliser les standards automatiques, il est impératif de noter les points suivants :

- Un standard automatique est requis pour disposer d’un compte de ressources associé. Pour plus d’informations sur les comptes de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .
- Si vous envisagez d’affecter un numéro d’acheminement direct, vous devez acquérir et attribuer les licences suivantes à \(votre compte de ressources Office 365 entreprise E1, E3 ou E5, à l’aide\)du composant additionnel du système téléphonique.
- Si vous affectez un numéro de service Microsoft à la place, vous devez acquérir et attribuer les licences suivantes à votre compte \(de ressources Office 365 entreprise E1, E3 ou E5, avec le module complémentaire du système téléphonique et un\)plan d’appels.
- Il vous suffit de créer une licence pour les comptes de ressources avec un numéro de téléphone qui leur est attribué. Dans une file d’attente d’appels ou de standards automatiques imbriqués, vous n’avez pas besoin de vous attribuer une licence au reste des standards automatiques ou des files d’attente d’appels s’ils ne disposent pas de numéros de téléphone associés. 

> [!NOTE]
> Les numéros de service de routage direct pour le standard automatique et les files d’attente d’appels sont uniquement pris en charge pour les utilisateurs et les agents Microsoft Teams.

> [!NOTE]
> Microsoft travaille sur un modèle de licence sans frais pour des applications telles que les standards automatiques de Cloud et les files d’attente d’appels, pour le moment, vous devez utiliser le modèle de gestion des licences utilisateur.
    
   > [!TIP]
   > Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne disposant d’une licence de **système téléphonique** , vous devez l’activer pour la voix entreprise ou lui affecter des plans d’appels. Voir [attribuer des licences Microsoft teams](assign-teams-licenses.md). Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour obtenir et utiliser des numéros de service gratuits pour vos standards automatiques, vous devez configurer des crédits de communication. Pour cela, voir [que sont les crédits de communication?](what-are-communications-credits.md) et [configurer les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des standards automatiques. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés.

- Un système de standard automatique complet implique généralement plusieurs standards automatiques et peut uniquement nécessiter un seul numéro de téléphone pour le standard automatique de niveau supérieur ou d’entrée. Les autres standards automatiques ou files d’attente d’appels dans le système complet ne nécessitent qu’un numéro de téléphone si vous souhaitez fournir plusieurs points d’entrée dans le système.
- Il est possible d’appliquer plusieurs numéros de téléphone à un standard automatique en associant plus d’un compte de ressources à un standard automatique.
  
## <a name="feature-overview"></a>Présentation de la fonctionnalité

### <a name="dial-by-name"></a>Numérotation par nom

La numérotation par nom est une fonctionnalité d’un standard automatique qui est également connu sous le nom de recherche dans l’annuaire. Elle permet aux personnes qui appellent votre standard automatique d’utiliser la reconnaissance vocale ou leur clavier téléphonique (DTMF) d’entrer un nom complet ou partiel pour rechercher dans l’annuaire de la société, de localiser la personne, puis de lui transférer l’appel. Les utilisateurs que vous souhaitez avoir localisés et pris en charge à l’aide de la numérotation par nom **n’ont pas besoin d’un numéro de téléphone ou**d’un plan d’appels est attribué aux utilisateurs de onpremises. La numérotation par nom sera même capable de rechercher et transférer des appels à des utilisateurs de Microsoft teams hébergés dans des pays ou des régions différents pour des organisations multinationales.

### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Il n’y a pas de limite de taille Active Directory pour lequel la numérotation par nom est prise en charge lorsque vous utilisez le clavier du téléphone pour rechercher la saisie de noms partiels ou complets (prénom + nom et également nom + prénom). Toutefois, la taille de liste de noms maximale qu’un standard automatique peut prendre en charge à l’aide de la reconnaissance vocale est de 80 000 utilisateurs.
  
|Type d'entrée|Format de recherche|Nombre maximal d'utilisateurs dans une organisation|
|:-----|:-----|:-----|
|DTMF (entrée de clavier de téléphone) |Partiel  <br/> Prénom + nom  <br/> Nom + prénom |Aucune limite  |
|Voix (entrée vocale) |Prénom  <br/> Ln  <br/> Prénom + nom  <br/> Nom + prénom  | 80 000 utilisateurs |

> [!NOTE]
> Si vous utilisez la fonction numérotation par nom avec la reconnaissance vocale, mais que le service Active Directory de votre organisation est supérieur à 80 000 utilisateurs et que vous n’avez pas limité l’étendue du numéro de téléphone à l’aide du clavier et les entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Les personnes appelant peuvent utiliser la numérotation par nom pour joindre les utilisateurs en spécifiant le nom complet ou partiel de la personne que vous essayez de joindre. Vous pouvez utiliser différents formats lorsque le nom est entré.

Lorsqu'ils recherchent dans l'annuaire de votre organisation, les utilisateurs peuvent utiliser la touche 0 (zéro) pour indiquer un espace entre le prénom et le nom ou vice versa. Lorsque vous entrez le nom, il est demandé d’arrêter son entrée au clavier à l’aide de la touche #. Par exemple : « Après avoir saisi le nom de la personne que vous voulez joindre, appuyez sur #. » Si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les employés peuvent rechercher des noms dans votre organisation à l'aide des formats de recherche suivants sur leur clavier téléphonique :
  
|Format de nom|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet  |Amos0Marble# |Amos Marble |
|Nom + prénom |Complet |Marble0Amos#  |Amos Marble |
|Prénom  |Complet   |Amos#   |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Ln |Complet |Marble#  |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Mary Marble |
|Prénom ou nom |Partiel |Mar# |Appuyez sur 1 pour Mary Marble  <br/> Appuyez sur 2 pour Mary Jones  <br/> Appuyez sur 3 pour Amos Marcus |
|Prénom + nom |Partiel |Mar0Amos# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Nom + prénom |Partiel |Mar0Am# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |

Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne sera invitée à utiliser la touche dièse (#), tandis que la touche zéro (0) est utilisée pour un espace entre les noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|Caractère spécial du clavier téléphonique|Signification|
|:-----|:-----|
|#   |Caractère de fin de saisie d'un nom |
|0,4   |Espace entre les noms |
|*    |Répétition de la liste de correspondances de noms |

### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Les personnes peuvent rechercher des personnes dans leur organisation à l’aide de leur voix (reconnaissance vocale). Ils peuvent également joindre tout le monde dans l’annuaire Active Directory de l’entreprise en indiquant le nom de la personne qu’il essaie de rechercher. L’utilisation des entrées vocales peut reconnaître les noms dans divers formats, dont prénom, nom, prénom + nom ou nom + prénom.
  
Lorsque vous activez la reconnaissance vocale pour un standard automatique, l’entrée de clavier téléphonique (DTMF) n’est pas désactivée, ce qui signifie que les deux types d’entrée peuvent être utilisés. Le clavier numérique ne peut pas être désactivé et peut être utilisé à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
Comme avec l'entrée de clavier téléphonique, si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les appelants peuvent prononcer les noms dans les formats suivants :
  
|Nom avec la reconnaissance vocale|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet |Amos Marble |Amos Marble |
|Nom + prénom |Complet  |Marble Amos |Amos Marble |
|Prénom |Complet |Amos |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones |
|Ln |Complet |Marble |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble |

> [!NOTE]
> Le nom d’un nouvel utilisateur peut nécessiter un délai de 36 heures (par nom) dans l’annuaire pour composer un numéro avec la reconnaissance vocale en raison d’un décalage de réplication Active Directory.
  
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
  
|Commande vocale| Correspond à |
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

L’utilisation de l’opérateur d’un standard automatique est un paramètre facultatif qui permet à l’appelant de parler à un opérateur humain.
  
La touche 0 et la commande vocale «opérateur» redirigent l’appel vers l’opérateur désigné par défaut. C’est le cas pour toutes les langues prises en charge par la reconnaissance vocale. Vous pouvez également utiliser les **options de menu** pour définir une valeur personnalisée pour l’opérateur.
  
L’opérateur peut être défini comme suit:
  
- Un utilisateur de Microsoft teams ou un utilisateur de Skype entreprise sur site qui est compatible voix entreprise.
  
- Un autre standard automatique configuré dans votre organisation
- Une file d'attente existante configurée dans votre organisation. Pour en savoir plus sur les files d’attente d’appels, voir [créer une file d’attente des appels Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Heures d'ouverture et traitement des appels

Les heures d'ouverture sont définies sur chaque standard automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures d’ouverture peuvent être définies à l’aide de pauses pendant la journée, et toutes les heures qui ne sont pas définies comme heures d’ouverture. Vous pouvez définir des options de traitement des appels entrantes différentes et des salutations différentes (facultatifs), et les deux peuvent être définies pour les heures d’activité et après l’heure.
  
Chaque standard automatique dispose d’options de traitement des appels qui peuvent être définies:
  
- Vous pouvez définir la déconnexion de l'appel juste après le message d'accueil.
- Vous pouvez également :
  - Rediriger l’appel vers un utilisateur de Microsoft teams disposant d’une licence de **système téléphonique** compatible voix entreprise ou dont les offres d’appels sont affectées. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.

  
  - Redirigez l’appel vers une file d’attente d’appels. Pour en savoir plus sur les files d’attente d’appels, voir [créer une file d’attente des appels Cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Rediriger l’appel vers un autre standard automatique que vous avez configuré.
- Créer des options de menu et activer une invite de menu pour l'appelant. Par exemple : « Appuyez sur 1 pour contacter le département des ventes, appuyez sur 2 pour contacter le département des services. Pour contacter l'opérateur, appuyez sur 0 à tout moment. »

### <a name="menu-options"></a>Options de menu

Les standards automatiques du Cloud vous permettent de créer des invites de menu («appuyer sur 1 pour les ventes, puis sur 2 pour les services») et de configurer les options de menu pour acheminer les appels en fonction de ce que l’utilisateur sélectionne. La configuration des options de menu d'un standard automatique permet à une organisation de fournir une assistance interactive pour orienter rapidement l'appelant vers sa destination, sans recourir à un opérateur humain pour la gestion des appels entrants. Les invites de menu peuvent être créées à l’aide de la conversion de texte par synthèse vocale ou du téléchargement d’un fichier audio qui a été enregistré. La reconnaissance vocale utilise des commandes vocales pour naviguer en mode mains libres, mais les appelants peuvent également utiliser leur clavier téléphonique pour parcourir les menus.
  
Les touches 0 à 9 peuvent être affectées à des **options de menu** dans un standard automatique à l’aide du centre d’administration Skype entreprise. Plusieurs ensembles d'options de menu peuvent être créés pour les heures d'ouverture et de fermeture et vous pouvez activer ou désactiver la fonction Numérotation par nom dans les **Options de menus**. Les touches peuvent être mappées pour transférer les appels vers :
  
- Un opérateur, mappé vers la touche 0 par défaut. Néanmoins, il peut être réattribué à une autre clé ou supprimé du menu.
- Une file d’attente d’appels.
- Un autre standard automatique. Les menus de plusieurs niveaux peuvent être configurés en pointant une **option de menu** dans un standard automatique vers un autre standard automatique doté de son propre ensemble d’options de menu, qui est appelé standard automatique «imbriqué».
- Un utilisateur de Microsoft teams disposant d’une licence de **système téléphonique** compatible voix entreprise ou dont les offres d’appels sont affectées. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
  
Le nom de chaque option de menu devient un mot clé de reconnaissance vocale si la reconnaissance vocale est activée. Par exemple, les appelants peuvent prononcer «un» pour sélectionner l’option de menu mappée à la clé 1 ou simplement «ventes» pour sélectionner la même option de menu «ventes».
  
Pour configurer un standard automatique et les options de menu, sélectionnez [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Attribution de numéros de téléphone pour un standard automatique

Vous pouvez affecter un numéro de service de plan d’appel Microsoft ou un numéro hybride de routage direct à votre standard automatique. Pour plus d’informations, voir [planifier le routage direct](direct-routing-plan.md) .

Pour attribuer un numéro de service, vous devez obtenir ou transférer vos numéros de service gratuits ou payants existants. Dès lors que vous recevez les numéros de service gratuits ou payants, ils s’affichent dans la <!-- validate nav path --> **** > Les**numéros de téléphone****vocaux** > du centre d’administration Skype entreprise et le **type de numéro** mentionné seront répertoriés en tant que **service-gratuit**. Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service pour Skype entreprise et Microsoft teams](/microsoftteams/getting-service-phone-numbers) ou, si vous voulez effectuer un virement et un numéro de service existant, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous résidez en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration de Microsoft teams pour obtenir des numéros de service. Pour savoir comment procéder, reportez-vous à la rubrique [gérer les numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .
  
## <a name="related-topics"></a>Voir aussi

[Voici les avantages du système téléphonique dans Office 365](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemple de petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)
