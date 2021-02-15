---
title: Que sont les attendants automatiques cloud ?
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: Découvrez les serveurs automatiques Cloud et comment les utiliser pour que les appelants se déplacent dans un système de menus pour localiser et passer ou transférer des appels à des utilisateurs ou services.
ms.openlocfilehash: 862272ffe0cb42edc092c513823f421ab1c5bd95
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918940"
---
# <a name="what-are-cloud-auto-attendants"></a>Que sont les attendants automatiques cloud ?

Phone System fournit des serveurs automatiques, qui peuvent être utilisés pour que les appelants externes et internes se déplacent dans un système de menus pour localiser et passer ou transférer des appels à des utilisateurs ou des services de votre organisation.
  
Un support automatique est le plus souvent un nœud dans un système, et il donne à l’appelant une série d’invites vocales ou de fichiers audio qu’il entend au lieu d’un opérateur humain. Lorsque des personnes appellent un numéro associé à un employé de service automatique, leurs choix peuvent rediriger l’appel vers un utilisateur ou rechercher une personne de votre organisation, puis se connecter à cet utilisateur. Ils peuvent exprimer leurs choix et interagir avec le système de menus à l’aide d’un clavier téléphonique (DTMF) ou d’une reconnaissance vocale. Les choix qu’ils font peuvent également rediriger l’appel vers un autre agent automatique ou vers une file d’attente d’appels.
  
Pour configurer un attendant automatique pour phone system, voir Configurer un attendant automatique [cloud.](create-a-phone-system-auto-attendant.md)
  
Un attendant automatique cloud offre les fonctionnalités suivantes :
  
- Il propose des messages d'accueil spécifiques de l'entreprise ou à vocation informative.
- Il propose des menus d'entreprise personnalisés. Vous pouvez personnaliser ces menus afin de disposer de plusieurs niveaux.
- Il fournit une recherche dans l’annuaire qui permet aux appelants de rechercher un nom dans l’annuaire de l’organisation.
- Il permet à une personne qui appelle de joindre ou de laisser un message à une personne de votre organisation.
- Il prend en charge plusieurs langues pour les invites, la reconnaissance vocale et la reconnaissance vocale.
- Il prend en charge la spécification de jours fériés et d’heures d’ouverture.
- Il prend en charge le transfert d’appel vers un opérateur, d’autres utilisateurs, des files d’attente d’appels et des files d’attente automatiques.
- Il prend en charge la messagerie vocale partagée pour que les appelants laissent un message pour une organisation.

> [!NOTE]
> Cet article s’applique à Microsoft Teams et à Skype Entreprise Online.

## <a name="getting-started"></a>Prise en main

Avant de commencer à utiliser les standards automatiques, il est impératif de noter les points suivants :

- Un attendant automatique est requis pour avoir un compte de ressource associé. Pour [plus d’informations](manage-resource-accounts.md) sur les comptes de ressources, voir Gérer les comptes de ressources dans Teams. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Lorsque vous affectez un numéro de téléphone à un employé de service automatique, vous l’affectez à proprement parler au compte de ressource associé à ce attendant automatique. Cela permet d’avoir plusieurs numéros de téléphone à accéder à un moyen automatique. Le plus souvent, un compte de ressource utilise la licence Utilisateur virtuel de Phone System sans frais. Cette licence offre des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation et vous permet de créer des numéros de service automatiques et des files d’attente d’appels.

> [!NOTE]
> Les numéros de service de routage direct pour le support automatique et les files d’attente d’appels sont pris en charge pour les utilisateurs de Microsoft Teams et les agents d’appel uniquement.

   > [!TIP]
   > Pour rediriger les appels vers un opérateur ou une option de menu qui est un utilisateur en ligne titulaire d’une licence **Phone System,** vous devez activer son compte pour les appels Voix Entreprise ou lui affecter des forfaits d’appels. Voir [Attribuer des licences de modules add-on Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Vous pouvez aussi utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Pour obtenir et utiliser des numéros de service gratuits pour vos postes de service automatiques, vous devez configurer les crédits de communication. Pour ce faire, voir Quels sont les [crédits de communication ?](what-are-communications-credits.md) et [configurer les crédits de communication pour votre organisation.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des standards automatiques. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés.

- Un système de attendant automatique complet implique généralement plusieurs attendants automatiques.
- Il est possible d’appliquer plusieurs numéros de téléphone aux attendant automatiques d’entrée.
- Les attendants automatiques ou files d’attente de niveau d’entrée dans le système complet n’auront besoin d’un numéro de téléphone que s’ils vont effectuer des appels RSTN sortants.
  
## <a name="feature-overview"></a>Vue d’ensemble de la fonctionnalité

### <a name="searching-for-users"></a>Recherche d’utilisateurs

La numérotation par nom est une fonctionnalité d’un service de service automatique également appelé recherche dans l’annuaire. Elle permet aux appelants d’utiliser la reconnaissance vocale ou leur clavier téléphonique (DTMF) pour saisir un nom complet ou partiel afin de rechercher dans l’annuaire de l’entreprise, de rechercher la personne et de lui transférer l’appel. Les utilisateurs que vous souhaitez avoir localisés et atteints à **l’aide** de la numérotation par nom ne doivent pas avoir de numéro de téléphone ou de forfaits d’appels, mais ils doivent avoir une licence De système téléphonique s’ils sont des utilisateurs en ligne ou Voix Entreprise activés pour les utilisateurs de Skype Entreprise Server. La numérotation par nom sera même en mesure de rechercher et de transférer des appels vers les utilisateurs de Microsoft Teams hébergés dans différents pays ou régions pour les organisations multinationales. Compte tenu des conditions préalables requises, vous activez explicitement la fonction Numérotation par nom dans un attendant automatique.

La numérotation par extension est une fonctionnalité d’un service de service automatique qui fait également partie de la recherche dans l’annuaire. Elle permet aux appelants d’utiliser la voix (reconnaissance vocale) ou leur clavier téléphonique (DTMF) pour saisir l’extension de téléphone de l’utilisateur qu’ils essaient de joindre, puis de transférer l’appel vers eux. Les utilisateurs que vous souhaitez avoir situés et que vous avez atteints à  **l’aide** de la numérotation par extension ne doivent pas avoir de numéro de téléphone ou de forfaits d’appels, mais ils doivent avoir une licence De système téléphonique s’ils sont des utilisateurs en ligne ou Voix Entreprise activés pour les utilisateurs de Skype Entreprise Server. Vous devrez également avoir un plan de numérotation correctement configuré pour vos utilisateurs. La numérotation par extension sera même en mesure de rechercher et de transférer des appels vers les utilisateurs de Microsoft Teams hébergés dans différents pays ou régions pour les organisations multinationales. Compte tenu des conditions préalables requises, vous devez activer explicitement la fonction Numérotation par poste dans un attendant automatique.

#### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Le nombre d’utilisateurs Active Directory dial by name and Dial by Extension peut être prise en charge lorsqu’un appelant recherche une personne en particulier. Un appelant peut entrer des noms partiels ou complets (Prénom + Nom, et également Nom + Prénom), mais il a besoin du numéro de poste complet. La taille de liste de noms maximale prise en charge par un seul employé de service automatique à l’aide de la reconnaissance vocale est de 80 000 utilisateurs.
  
|Type d'entrée|Format de recherche|Nombre maximal d'utilisateurs dans une organisation|
|:-----|:-----|:-----|
|DTMF (entrée de clavier de téléphone) |Partiel  <br/> Prénom + nom  <br/> Nom + prénom |Aucune limite  |
|Voix (entrée vocale) |Prénom  <br/> Nom  <br/> Prénom + nom  <br/> Nom + prénom  | 80 000 utilisateurs |

> [!NOTE]
> Si vous utilisez la fonction Numérotation par nom avec la reconnaissance vocale, mais que l’Active Directory de votre organisation compte plus de 80 000 utilisateurs et que vous n’avez pas limité l’étendue de la numérotation par nom à l’aide de la fonctionnalité de portée de la numérotation, la fonction Numérotation par nom continuera de fonctionner pour vos appelants à l’aide d’un clavier téléphonique et les entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Les appelants peuvent utiliser la numérotation par nom pour joindre des utilisateurs en spécifiant leur nom complet ou partiel. Plusieurs formats peuvent être utilisés lorsque le nom est entré.

Lorsqu'ils recherchent dans l'annuaire de votre organisation, les utilisateurs peuvent utiliser la touche 0 (zéro) pour indiquer un espace entre le prénom et le nom ou vice versa. Lorsqu’il entre le nom, il est invité à terminer son entrée de clavier par la touche #. Par exemple : « Après avoir saisi le nom de la personne que vous voulez joindre, appuyez sur #. » Si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.
  
Les employés peuvent rechercher des noms dans votre organisation à l'aide des formats de recherche suivants sur leur clavier téléphonique :
  
|Format de nom|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet  |Amos0Marble# |Amos Marble |
|Nom + prénom |Complet |Marble0Amos#  |Amos Marble |
|Prénom  |Complet   |Amos#   |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Nom |Complet |Marble#  |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Mary Marble |
|Prénom ou nom |Partiel |Mar# |Appuyez sur 1 pour Mary Marble  <br/> Appuyez sur 2 pour Mary Jones  <br/> Appuyez sur 3 pour Amos Marcus |
|Prénom + nom |Partiel |Amos0Mar # |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Nom + prénom |Partiel |Mar0Am# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |

Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne sera invitée à utiliser la touche di clés (#), tandis que la touche zéro (0) est utilisée pour l’espace entre les noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|Caractère spécial du clavier téléphonique|Signification|
|:-----|:-----|
|#   |Caractère de fin de saisie d'un nom |
|0   |Espace entre les noms |
|*    |Répétition de la liste de correspondances de noms |

#### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Les employés peuvent rechercher d’autres personnes dans leur organisation à l’grâce à leur voix (reconnaissance vocale). Ils peuvent également joindre n’importe qui dans Active Directory en en att ressant le nom de la personne qu’ils cherchent. Les entrées vocales peuvent reconnaître les noms dans différents formats, notamment Prénom, Nom, Prénom + Nom, ou Nom + Prénom.
  
Vous pouvez activer la reconnaissance vocale pour un attendant automatique, mais l’entrée de clavier téléphonique (DTMF) n’est pas désactivée. Vous pouvez utiliser une entrée de clavier téléphonique à tout moment, même si la reconnaissance vocale est activée sur le attendant automatique.
  
Comme pour l’entrée de clavier téléphonique, si plusieurs noms sont trouvés, l’appelant entend une liste de noms parmi qui vous sont demandés.
  
Les appelants peuvent dire les noms dans les formats suivants :
  
|Nom avec reconnaissance vocale|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet |Amos Marble |Amos Marble |
|Nom + prénom |Complet  |Marble Amos |Amos Marble |
|Prénom |Complet |Amos |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones |
|Nom |Complet |Marble |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble |

> [!NOTE]
> Jusqu’à 36 heures peuvent être nécessaire pour que le nom d’un nouvel utilisateur soit répertorié dans l’annuaire pour la numérotation par nom avec une reconnaissance vocale en raison d’un décalage de réplication Active Directory.
  
### <a name="language-support"></a>Prise en charge des langues

Les langues suivantes sont disponibles pour la reconnaissance vocale utilisée avec les invites sortantes :
  
|A-E|E-J|K-Z|
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

L’entrée de reconnaissance vocale pour les attendants automatiques est disponible dans les langues suivantes :
  
|A-F|F-Z|
|:-----|:-----|
|Chinois (ZH)  |Français (FR)  |
|Anglais (AU)  |Allemand (DE)  |
|Anglais (CA)  |Italien (IT)  |
|Anglais (IN)  |Japonais (JP)  |
|Anglais (Royaume-Uni)  |Portugais (BR)  |
|Anglais (É.U.)  |Espagnol (ES)  |
|Français (CA)   |Espagnol (MX)  |

Les commandes vocales suivantes sont disponibles dans les 14 langues prise en charge pour la reconnaissance vocale :
  
|Commande vocale| Correspond à |
|:-----|:-----|
|Oui | Appuyez sur 1 pour appuyer sur Oui. |
|Non | Appuyez sur 2 pour non. |
|Répéter |Répète la liste des options. Appuyez sur * sur le pavé numérique pour répéter la liste des options. |
|Opérateur | Appuyez sur 0 pour « Opérateur » |
|Menu principal  |Dirige l'appelant vers le menu principal du standard automatique. |
|Zéro | Appuyez sur 0 (par défaut, identique à « Opérateur »).|
|Un | Appuyez sur 1. |
|Deux | Appuyez sur 2. |
|Trois| Appuyez sur 3.|
|Quatre | Appuyez sur 4. |
|Cinq | Appuyez sur 5. |
|Six  | Appuyez sur 6. |
|Sept | Appuyez sur 7.|
|Huit |Appuyez sur 8.|
|Neuf  |Appuyez sur 9.|

### <a name="the-operator-option"></a>L’option opérateur

Un attendant automatique peut éventuellement être sélectionné pour que l’appelant parle à un opérateur.
  
La touche 0 et la commande vocale « Opérateur » dirigent l’appel vers l’opérateur désigné par défaut. C’est le cas pour toutes les langues prise en charge pour la reconnaissance vocale. Vous pouvez également utiliser les **options de menu Définir** pour définir une valeur personnalisée pour l’opérateur.
  
L’opérateur peut être définie sur :
  
- Utilisateur de Microsoft Teams ou de Skype Entreprise Server Voix Entreprise activé.
- Un autre standard automatique configuré dans votre organisation
- Une file d'attente existante configurée dans votre organisation. Pour en savoir plus sur les files d’attente d’appels, voir [Créer une file d’attente d’appels cloud.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Heures d'ouverture et traitement des appels

Les heures d’ouverture peuvent être définies sur chaque attendant automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures d’ouverture peuvent être définies avec des pauses au cours de la journée et toutes les heures non définies comme heures d’ouverture sont considérées comme des heures d’ouverture en de suite. Vous pouvez définir différentes options de traitement des appels entrants et différents messages d’accueil (facultatifs) pour les heures d’ouverture et de fin d’activité.
  
Chaque employé automatique dispose de plusieurs options de traitement des appels possibles :
  
- L’appel peut se déconnecter après la fin de la première salutation.
- Vous pouvez également :
  - Rediriger l’appel vers un utilisateur de Microsoft Teams qui dispose d’une licence **Système** téléphonique Voix Entreprise activé ou à qui des plans d’appels ont été attribués. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.

  - Rediriger l’appel vers une file d’attente d’appels. Pour en savoir plus sur les files d’attente d’appels, voir [Créer une file d’attente d’appels cloud.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Rediriger l’appel vers un autre service de service automatique.

Ces options sont expressément exprimées pour l’appelant par le personnel automatique lorsqu’il lit les invites du menu. Par exemple : « Appuyez sur 1 pour le chiffre d’affaires, sur 2 pour les services. Pour parler à l’opérateur, appuyez sur 0 à tout moment. »

### <a name="set-menu-options"></a>Définir les options du menu

Les attendant automatiques cloud vous permettent de créer des invites de menu (« Appuyez sur 1 pour appuyer sur 1 pour appeler les ventes, appuyez sur 2 pour appeler les services ») et de configurer des options de menu pour router les appels en fonction des sélections d’utilisateurs. Les options de menu d’un employé de service automatique permettent à une organisation de fournir une série de choix qui guident les appelants vers leur destination plus rapidement, sans faire appel à un opérateur humain pour gérer les appels entrants. Les invites de menu peuvent être créées à l’aide de la reconnaissance vocale (invites générées par le système) ou en téléchargeant un fichier audio enregistré. La reconnaissance vocale accepte les commandes vocales pour une navigation mains libres, mais les appelants peuvent également utiliser le clavier téléphonique pour naviguer dans les menus.
  
Les touches 0 à 9 peuvent être affectées aux touches de numérotation d’un moyen de service automatique à l’aide du Centre d’administration de Skype Entreprise. Plusieurs ensembles d'options de menu peuvent être créés pour les heures d'ouverture et de fermeture et vous pouvez activer ou désactiver la fonction Numérotation par nom dans les **Options de menus**. Les touches peuvent être mappées pour transférer les appels vers :
  
- Un opérateur, mappé vers la touche 0 par défaut. Toutefois, il peut être réasigné à une autre touche ou supprimé du menu.
- Une file d’attente d’appels.
- Un autre standard automatique. Vous pouvez configurer des menus à plusieurs niveaux en pointant une **option** de menu dans un employé de service automatique vers un autre attendant automatique avec son propre ensemble d’options de menu, également appelé de « attendant automatique imbrmbré ».
- Un utilisateur de Microsoft Teams qui dispose d’une licence **Phone System** Voix Entreprise est activée ou à qui des plans d’appel ont été attribués. Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale. Pour ce faire, sélectionnez **une personne de votre entreprise** et configurez ses appels pour les rediriger automatiquement vers la messagerie vocale.
  
Le nom de chaque option de menu devient un mot clé de reconnaissance vocale si la reconnaissance vocale a été activée. Par exemple, les appelants peuvent dire « Un » pour sélectionner l’option de menu mappée vers la touche 1, ou dire « Ventes » pour sélectionner la même option de menu appelée « Ventes ».
  
Pour configurer un attendant automatique et les options de menu, allez [configurer un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Affectation de numéros de téléphone pour un employé de service automatique

Vous pouvez affecter un numéro de service Microsoft, un numéro de routage direct ou un numéro hybride au compte de ressource lié de votre employé automatique (ou à plusieurs comptes de ressources si plusieurs numéros de téléphone sont souhaités). Pour [plus d’informations, voir Routage](direct-routing-plan.md) direct du plan.

Pour attribuer un numéro de service, vous devez obtenir ou porter vos numéros de service gratuits ou gratuits existants. Une fois que vous obtenez les numéros de téléphone des services gratuits ou gratuits, ils s’afficheront dans les numéros de téléphone vocux du Centre d’administration **Skype**  >    >  **Entreprise.** **Le type de** numéro est répertorié **comme Service - Gratuit.** Pour obtenir vos numéros de service, consultez Obtenir des numéros de téléphone de service pour Skype Entreprise et [Microsoft Teams](/microsoftteams/getting-service-phone-numbers) ou, si vous souhaitez transférer un numéro de service existant, consultez Transférer les numéros de téléphone dans [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le Centre d’administration Microsoft Teams pour obtenir des numéros de service. Allez [à Gérer les numéros de téléphone pour votre](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) organisation à la place pour voir comment le faire.
  
## <a name="related-topics"></a>Sujets associés

[Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
