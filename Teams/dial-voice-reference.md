---
title: Mise en attente des appels et de la reconnaissance vocale
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: En savoir plus sur le standard automatique et les options de numérotation de la file d’attente et de reconnaissance vocale dans Teams.
ms.openlocfilehash: bf520fa4dffe258da523c8815449f1e71279d7f2
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800567"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Mise en attente des appels et de la reconnaissance vocale

La numérotation par nom est une fonctionnalité d’un standard automatique qui est également connu sous le nom de recherche dans l’annuaire. Elle permet aux personnes qui appellent votre standard automatique d’utiliser la reconnaissance vocale ou leur clavier téléphonique (DTMF) d’entrer un nom complet ou partiel pour rechercher dans l’annuaire de la société, de localiser la personne, puis de lui transférer l’appel. Vous avez configuré la numérotation par nom lorsque vous [configurez les paramètres du flux d’appels dans un standard automatique](create-a-phone-system-auto-attendant.md#call-flow).

## <a name="searching-for-users"></a>Rechercher des utilisateurs

Les utilisateurs que vous souhaitez avoir localisés et pris en charge à l’aide de la numérotation par nom **n’ont pas besoin d’un numéro de téléphone ou d’un plan d’appels est attribué aux utilisateurs de Skype entreprise Server** . La numérotation par nom sera même capable de rechercher et transférer des appels à des utilisateurs de Microsoft teams hébergés dans des pays ou des régions différents pour des organisations multinationales. En fonction des éléments requis, vous activez explicitement la numérotation par nom dans un standard automatique.

Dial by extension est une fonctionnalité d’un standard automatique qui fait également partie de la recherche dans l’annuaire. Elle permet aux personnes qui rejoignent votre standard automatique d’utiliser la reconnaissance vocale (Speech) ou leur clavier téléphonique (DTMF) d’entrer l’extension du téléphone de l’utilisateur que vous essayez de joindre, puis de lui transférer l’appel. Les utilisateurs que vous souhaitez trouver et auxquels il est possible d’accéder à l’aide de la numérotation par poste  **ne doivent pas être associés à un numéro de téléphone ou être associés à des plans d’appel, mais ils doivent disposer d’une licence de système téléphonique s’il s’agit d’utilisateurs en ligne ou d’Enterprise Voice activé pour les utilisateurs de Skype entreprise Server** . Vous devrez également disposer d’un plan de numérotation correctement configuré pour vos utilisateurs. Le numérotation par poste de passe peut même être capable de rechercher et transférer des appels à des utilisateurs de Microsoft teams hébergés dans différents pays ou régions d’organisations multinationales. En fonction des éléments requis concernés, vous activez explicitement Dial par extension dans un standard automatique.

### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Il n’y a aucune limite au nombre de utilisateurs de la fonction de numérotation par nom et par extension peut prendre en charge quand un appelant recherche une personne spécifique. Un appelant peut entrer des noms partiels ou complets (prénom + nom, et également nom + prénom), mais doit avoir le numéro de poste complet. La taille de liste de noms maximale qu’un standard automatique peut prendre en charge à l’aide de la reconnaissance vocale est de 80 000 utilisateurs.
  
|Type d'entrée|Format de recherche|Nombre maximal d'utilisateurs dans une organisation|
|:-----|:-----|:-----|
|DTMF (entrée de clavier de téléphone) |Partiel  <br/> Prénom + nom  <br/> Nom + prénom |Aucune limite  |
|Voix (entrée vocale) |Prénom  <br/> Ln  <br/> Prénom + nom  <br/> Nom + prénom  | 80 000 utilisateurs |

> [!NOTE]
> Si vous utilisez la fonction numérotation par nom avec la reconnaissance vocale, mais que le service Active Directory de votre organisation est supérieur à 80 000 utilisateurs et que vous n’avez pas limité l’étendue de la numérotation par nom à l’aide de la fonctionnalité d’étendue de numérotation, la numérotation par nom restera valable pour les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)
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
|Prénom + nom |Partiel |Amos0Mar # |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Nom + prénom |Partiel |Mar0Am# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |

Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne sera invitée à utiliser la touche dièse (#), tandis que la touche zéro (0) est utilisée pour un espace entre les noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|Caractère spécial du clavier téléphonique|Signification|
|:-----|:-----|
|#   |Caractère de fin de saisie d'un nom |
|0,4   |Espace entre les noms |
|*    |Répétition de la liste de correspondances de noms |

### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Les personnes peuvent effectuer des recherches dans leur organisation par le biais de leur voix (reconnaissance vocale). Ils peuvent également joindre tout le monde dans Active Directory en indiquant le nom de la personne qu’il essaie de rechercher. L’utilisation des entrées vocales peut reconnaître les noms dans divers formats, dont prénom, nom, prénom + nom ou nom + prénom.
  
Vous pouvez activer la reconnaissance vocale pour un standard automatique, mais celle-ci n’est pas désactivée. Le clavier numérique peut être utilisé à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
Comme avec l’entrée de clavier téléphonique, si plusieurs noms sont trouvés, la personne qui appelle entend une liste de noms parmi lesquels sélectionner.
  
Les appelants peuvent prononcer les noms dans les formats suivants :
  
|Nom avec la reconnaissance vocale|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet |Amos Marble |Amos Marble |
|Nom + prénom |Complet  |Marble Amos |Amos Marble |
|Prénom |Complet |Amos |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones |
|Ln |Complet |Marble |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble |

> [!NOTE]
> Le nom d’un nouvel utilisateur peut nécessiter un délai de 36 heures (par nom) dans l’annuaire pour composer un numéro avec la reconnaissance vocale en raison d’un décalage de réplication Active Directory.
  
## <a name="language-support"></a>Prise en charge des langues

Les langues suivantes sont disponibles pour la synthèse vocale utilisée avec les invites de courrier :
  
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

L’entrée de reconnaissance vocale pour les standards automatiques est disponible dans les langues suivantes :
  
|||
|:-----|:-----|
|Chinois (ZH)  |Français (FR)  |
|Anglais (AU)  |Allemand (DE)  |
|Anglais (CA)  |Italien (IT)  |
|Anglais (IN)  |Japonais (JP)  |
|Anglais (Royaume-Uni)  |Portugais (BR)  |
|Anglais (É.U.)  |Espagnol (ES)  |
|Français (CA)   |Espagnol (MX)  |

Les commandes vocales suivantes sont disponibles dans les 14 langues prises en charge par la reconnaissance vocale :
  
|Commande vocale| Correspond à |
|:-----|:-----|
|Oui | Tapez 1 pour Oui. |
|Non | Tapez 2 pour non. |
|Répéter |Répète la liste des options. Dans le pavé numérique, appuyez sur * pour répéter la liste des options. |
|Opérateur | Appuyez sur 0 pour « opérateur ». |
|Menu principal  |Dirige l'appelant vers le menu principal du standard automatique. |
|Zéro | Appuyez sur 0 (par défaut, identique à « opérateur »).|
|Un | Appuyez sur 1. |
|Deux | Tapez 2. |
|Trois| Tapez 3.|
|Quatre | Appuyez sur 4. |
|Cinq | Appuyez sur 5. |
|Six  | Appuyez sur 6. |
|Sept | Appuyez sur 7.|
|Huit |Appuyez sur 8.|
|Neuf  |Appuyez sur 9.|

## <a name="related-topics"></a>Sujets associés

[Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Exemple de petite entreprise : configurer un standard automatique](/microsoftteams/tutorial-org-aa)
