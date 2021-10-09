---
title: Référence de la reconnaissance vocale et de la numérotation automatique et de la file d’attente des appels
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: En savoir plus sur les options de numérotation automatique et de reconnaissance vocale de la file d’attente dans Teams.
ms.openlocfilehash: acd3202a3f27beaf40af09422687be490f0695c5
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249686"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Référence de la reconnaissance vocale et de la numérotation automatique et de la file d’attente des appels

La numérotation par nom est une fonctionnalité d’un service de service automatique également appelé recherche dans l’annuaire. Elle permet aux appelants d’utiliser la reconnaissance vocale ou leur clavier téléphonique (DTMF) pour saisir un nom complet ou partiel afin de rechercher dans l’annuaire de l’entreprise, de rechercher la personne et de lui transférer l’appel. Vous configurez la numérotation par nom lorsque vous configurez les paramètres du flux [d’appels dans un attendant automatique.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Recherche d’utilisateurs

Les utilisateurs que vous souhaitez avoir localisés et atteints à l’aide de la numérotation par nom ne doivent pas avoir de numéro de téléphone ou de forfaits d’appels, mais ils doivent être Voix Entreprise pour Skype Entreprise Server **utilisateurs.** La numérotation par nom sera même en mesure de rechercher et de transférer des appels vers Microsoft Teams utilisateurs hébergés dans différents pays ou régions pour des organisations multinationales. Compte tenu des conditions préalables requises, vous activez explicitement la fonction Numérotation par nom dans un attendant automatique.

La numérotation par poste est une fonctionnalité d’un service de service automatique qui fait également partie de la recherche dans l’annuaire. Elle permet aux appelants d’utiliser la voix (reconnaissance vocale) ou leur clavier téléphonique (DTMF) pour saisir l’extension de téléphone de l’utilisateur qu’ils essaient de joindre, puis de transférer l’appel vers eux. Les utilisateurs que vous souhaitez avoir situés et que vous avez atteints à l’aide de la numérotation par extension ne doivent pas avoir de numéro de téléphone ou de forfaits d’appels, mais ils doivent être Voix Entreprise pour Skype Entreprise Server **utilisateurs.** Vous devrez également avoir un plan de numérotation correctement configuré pour vos utilisateurs. La numérotation par extension sera même en mesure de rechercher et de transférer des appels vers Microsoft Teams utilisateurs hébergés dans différents pays ou régions pour des organisations multinationales. Compte tenu des conditions préalables requises, vous activez explicitement la fonction Numérotation par poste dans un attendant automatique.

### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Il n’y a pas de limite au nombre d’utilisateurs Active Directory que les appels peuvent prendre en charge lorsqu’un appelant recherche une personne en particulier. Un appelant peut entrer des noms partiels ou complets (Prénom + Nom, et également Nom + Prénom), mais il a besoin du numéro de poste complet. La taille de liste de noms maximale prise en charge par un seul employé de service automatique à l’aide de la reconnaissance vocale est de 80 000 utilisateurs.
  
|Type d'entrée|Format de recherche|Nombre maximal d'utilisateurs dans une organisation|
|:-----|:-----|:-----|
|DTMF (entrée de clavier de téléphone) |Partiel  <br/> Prénom + nom  <br/> Nom + prénom |Aucune limite  |
|Voix (entrée vocale) |Prénom  <br/> Nom  <br/> Prénom + nom  <br/> Nom + prénom  | 80 000 utilisateurs |

> [!NOTE]
> Si vous utilisez la fonction Numérotation par nom avec la reconnaissance vocale, mais que l’Active Directory de votre organisation compte plus de 80 000 utilisateurs et que vous n’avez pas limité l’étendue de la numérotation par nom à l’aide de la fonctionnalité de portée de la numérotation, la fonction Numérotation par nom continuera de fonctionner pour vos appelants à l’aide d’un clavier téléphonique et les entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)
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

### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Les employés peuvent rechercher d’autres personnes dans leur organisation à l’grâce à leur voix (reconnaissance vocale). Ils peuvent également joindre n’importe qui dans Active Directory en leur att dit leur nom complet ou partiel. Les entrées vocales peuvent reconnaître les noms dans différents formats, notamment Prénom, Nom, Prénom + Nom, ou Nom + Prénom.
  
Vous pouvez activer la reconnaissance vocale pour un attendant automatique, mais l’entrée de clavier téléphonique (DTMF) n’est pas désactivée. Téléphone entrée de clavier automatique peut être utilisée à tout moment, même si la reconnaissance vocale est activée sur le attendant automatique.
  
Comme pour l’entrée de clavier téléphonique, si plusieurs noms sont trouvés, l’appelant entend une liste de noms parmi qui vous sont demandés.
  
Les appelants peuvent dire les noms dans les formats suivants :
  
|Nom avec reconnaissance vocale|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet |Amos Marble |Amos Marble |
|Nom + prénom |Complet  |Marble Amos |Amos Marble |
|Prénom |Complet |Amos |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones |
|Nom |Complet |Marble |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble |
|Prénom ou nom |Partiel |Mars |Appuyez sur 1 ou dites 1 pour Mary Marble  <br/> Appuyez sur 2 ou dites 1 pour Mary Jones  <br/> Appuyez sur 3 ou dites 3 pour AmosMos (Qu’est-ce que vous dites ) ? |
|Prénom + nom |Partiel |Amos Mar |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour AmosEz |


> [!NOTE]
> Jusqu’à 36 heures peuvent être nécessaire pour que le nom d’un nouvel utilisateur soit répertorié dans l’annuaire pour la numérotation par nom avec une reconnaissance vocale en raison d’un décalage de réplication Active Directory.
  
## <a name="language-support"></a>Prise en charge des langues

La prise en charge linguistique de la reconnaissance vocale et de la reconnaissance vocale est disponible dans ces [langues.](create-a-phone-system-auto-attendant-languages.md)

Les commandes vocales suivantes sont disponibles pour la reconnaissance vocale : 
  
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

## <a name="related-topics"></a>Sujets associés

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
