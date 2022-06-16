---
title: Référence de numérotation et de reconnaissance vocale du standard automatique et de la file d’attente d’appels
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
description: Découvrez les options de numérotation et de reconnaissance vocale du standard automatique et de la file d’attente des appels dans Teams.
ms.openlocfilehash: 784dcbf16c5122c165dc1a949fa237769c9837d3
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124189"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Référence de numérotation et de reconnaissance vocale du standard automatique et de la file d’attente d’appels

Numérotation par nom ou par extension est une fonctionnalité de standard automatique qui permet aux appelants d’atteindre Teams utilisateurs de votre organisation. À l’aide de leur clavier vocal ou téléphonique, les appelants peuvent indiquer ou entrer le nom complet ou partiel, ou l’extension de la personne qu’ils souhaitent joindre. Le standard automatique effectue une recherche dans le répertoire de l’entreprise, recherche la personne, puis lui transfère l’appelant.  Numérotation par nom ou numérotation par extension sont des options que vous configurez lorsque vous [configurez les paramètres de flux d’appel dans un standard automatique](create-a-phone-system-auto-attendant.md?tabs=call-flow).

## <a name="searching-for-users"></a>Recherche d’utilisateurs

Teams les utilisateurs qui peuvent être contactés à l’aide de Dial by Name **ne sont pas tenus d’avoir un numéro de téléphone ou d’avoir des forfaits d’appels qui leur sont attribués, mais ils doivent être Voix Entreprise activés pour Skype Entreprise Server utilisateurs**. Pour les organisations multinationales, Dial by Name recherche et transfère les appelants vers Microsoft Teams utilisateurs qui se trouvent dans des pays ou régions différents.

Teams utilisateurs qui peuvent être contactés à l’aide de Dial by Extension **ne sont pas tenus d’avoir un numéro de téléphone ou d’avoir des forfaits d’appels qui leur sont attribués, mais ils doivent être Voix Entreprise activés pour Skype Entreprise Server utilisateurs**. Vous devez également disposer d’un plan de numérotation correctement configuré pour vos utilisateurs. Pour les organisations multinationales, Dial by Extension recherche et transfère les appelants vers Microsoft Teams utilisateurs qui se trouvent dans différents pays ou régions.

Compte tenu des conditions préalables requises, la numérotation par nom ou par extension doit être explicitement activée lors de la configuration d’un standard automatique.

### <a name="maximum-directory-size"></a>Taille de l'annuaire maximale

Le nombre d’utilisateurs Active Directory composés par nom et numérotation par extension ne peut pas être pris en charge lorsqu’un appelant recherche une personne spécifique. Un appelant peut entrer des noms partiels ou complets (FirstName + LastName, ainsi que LastName + FirstName), mais a besoin du numéro d’extension complet. La taille maximale de liste de noms qu’un standard automatique unique peut prendre en charge à l’aide de la reconnaissance vocale est de 80 000 utilisateurs.
  
|Type d'entrée|Format de recherche|Nombre maximal d'utilisateurs dans une organisation|
|:-----|:-----|:-----|
|DTMF (entrée de clavier de téléphone) |Partiel  <br/> Prénom + nom  <br/> Nom + prénom |Aucune limite  |
|Voix (entrée vocale) |Prénom  <br/> Lastname  <br/> Prénom + nom  <br/> Nom + prénom  | 80 000 utilisateurs |

> [!NOTE]
> Si vous utilisez Dial by Name avec reconnaissance vocale, mais que l’annuaire Active Directory de votre organisation compte plus de 80 000 utilisateurs et que vous n’avez pas limité l’étendue de Numérotation par nom à l’aide de la fonctionnalité [Portée de numérotation](create-a-phone-system-auto-attendant.md?tabs=dial-scope) , dial by Name fonctionnera toujours pour vos appelants à l’aide d’un clavier téléphonique et les entrées vocales seront disponibles pour tous les autres scénarios. Vous pouvez utiliser la fonctionnalité de Portée de la numérotation pour limiter les noms atteignables en modifiant la portée de la Numérotation par nom pour un standard automatique spécifique.

### <a name="search-considerations"></a>Considérations relatives à la recherche

La fonction Numérotation par nom effectue d’abord une recherche dans l’annuaire de l’ensemble de l’organisation avant d’appliquer les listes Include ou Exclude de l’étendue de numérotation qui ont été configurées. Si la recherche initiale sur l’ensemble du répertoire retourne plus de 100 utilisateurs, les listes d’étendue de numérotation ne sont pas appliquées, la recherche échoue et l’appelant est informé que trop de noms ont été trouvés.

## <a name="dial-by-name---keypad-dtmf-entry"></a>Numérotation par nom - Entrée de clavier téléphonique (DTMF)

Les personnes qui appellent peuvent utiliser Dial by Name pour atteindre les utilisateurs en spécifiant le nom complet ou partiel de la personne qu’elles tentent d’atteindre. Il existe différents formats qui peuvent être utilisés lorsque le nom est entré.

Lorsqu'ils recherchent dans l'annuaire de votre organisation, les utilisateurs peuvent utiliser la touche 0 (zéro) pour indiquer un espace entre le prénom et le nom ou vice versa. Lorsqu’ils entrent le nom, ils sont invités à terminer leur entrée de clavier avec la touche # . Par exemple : « Après avoir saisi le nom de la personne que vous voulez joindre, appuyez sur #. » Si la recherche renvoie plusieurs noms, l'appelant pourra en sélectionner un parmi une liste.

> [!NOTE]
> Si plus de 5 noms demeurent après l’application de listes Include ou Exclude de l’étendue de numérotation, la recherche échoue et l’appelant est informé que trop de noms ont été trouvés.
  
Les employés peuvent rechercher des noms dans votre organisation à l'aide des formats de recherche suivants sur leur clavier téléphonique :
  
|Format de nom|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet  |Amos0Marble# |Amos Marble |
|Nom + prénom |Complet |Marble0Amos#  |Amos Marble |
|Prénom  |Complet   |Amos#   |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Lastname |Complet |Marble#  |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Mary Marble |
|Prénom ou nom |Partiel |Mar# |Appuyez sur 1 pour Mary Marble  <br/> Appuyez sur 2 pour Mary Jones  <br/> Appuyez sur 3 pour Amos Marcus |
|Prénom + nom |Partiel |Amos0Mar # |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |
|Nom + prénom |Partiel |Mar0Am# |Appuyez sur 1 pour Amos Marble  <br/> Appuyez sur 2 pour Amos Marcus |

Plusieurs caractères spéciaux sont utilisés pour rechercher des personnes à l'aide d'un clavier téléphonique. Par exemple, la personne est invitée à utiliser la touche pound (#), tandis que la touche zéro (0) est utilisée pour un espace entre les noms. Appuyer sur la touche étoile (*) permet de répéter la liste des correspondances de noms.
  
|Caractère spécial du clavier téléphonique|Signification|
|:-----|:-----|
|#   |Caractère de fin de saisie d'un nom |
|0   |Espace entre les noms |
|*    |Répétition de la liste de correspondances de noms |

### <a name="dial-by-name---name-recognition-with-speech"></a>Numérotation par nom - Reconnaissance vocale de nom

Les utilisateurs peuvent rechercher d’autres membres de leur organisation avec leur voix (reconnaissance vocale). Ils peuvent également joindre n’importe qui dans Active Directory en indiquant le nom complet ou partiel de la personne qu’ils tentent de localiser. L’utilisation d’entrées vocales peut reconnaître des noms dans différents formats, notamment FirstName, LastName, FirstName + LastName ou LastName + FirstName.
  
Vous pouvez activer la reconnaissance vocale pour un standard automatique, mais l’entrée du clavier téléphonique (DTMF) n’est pas désactivée. Téléphone entrée de clavier peut être utilisée à tout moment, même si la reconnaissance vocale est activée sur le standard automatique.
  
Comme pour l’entrée du clavier téléphonique, si plusieurs noms sont trouvés, la personne qui appelle entend une liste de noms à sélectionner.

> [!NOTE]
> Si plus de 5 noms demeurent après l’application de listes Include ou Exclude de l’étendue de numérotation, la recherche échoue et l’appelant est informé que trop de noms ont été trouvés.
  
Les appelants peuvent dire des noms dans les formats suivants :
  
|Nom avec reconnaissance vocale|Type de recherche|Exemple|Résultat de recherche|
|:-----|:-----|:-----|:-----|
|Prénom + nom |Complet |Amos Marble |Amos Marble |
|Nom + prénom |Complet  |Marble Amos |Amos Marble |
|Prénom |Complet |Amos |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Amos Jones |
|Lastname |Complet |Marble |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez sur 2 ou dites 1 pour Ben Marble |
|Prénom ou nom |Partiel |Mar |Appuyez ou dites 1 pour Mary Marble  <br/> Appuyez ou dites 2 pour Mary Jones  <br/> Appuyez ou dites 3 pour Amos Marcus |
|Prénom + nom |Partiel |Amos Mar |Appuyez sur 1 ou dites 1 pour Amos Marble  <br/> Appuyez ou dites 2 pour Amos Marcus |

> [!NOTE]
> Il peut prendre jusqu’à 36 heures pour qu’un nouvel utilisateur ait son nom répertorié dans le répertoire numérotation par nom avec reconnaissance vocale en raison du décalage de réplication Active Directory.

### <a name="dial-by-extension"></a>Composer par extension

Les utilisateurs que vous souhaitez rendre disponibles pour **la numérotation par extension** doivent avoir une extension spécifiée dans le cadre de l’un des attributs de téléphone suivants définis dans Active Directory (et synchronisés via Azure AD Connecter) ou Azure Active Directory. (Pour plus d’informations, consultez [Ajouter des utilisateurs individuellement ou en bloc](/microsoft-365/admin/add-users/add-users) .)

- OfficePhone/TelephoneNumber (AD et Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD et Azure AD)
- OtherTelephone (AD)

Le format requis pour entrer l’extension dans le champ numéro de téléphone de l’utilisateur peut être l’un des formats suivants :

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Exemple 1 : Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber « +15555555678;ext=5678 »
- Exemple 2 : Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber « +1555555678x5678 »
- Exemple 3 : Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber « x5678 »

Vous pouvez définir l’extension dans le [Centre d'administration Microsoft 365](https://admin.microsoft.com/) ou le [centre d’administration Azure Active Directory](https://aad.portal.azure.com). Jusqu’à 12 heures peuvent être nécessaires avant que les modifications ne soient disponibles pour les standards automatiques et les files d’attente d’appels.

## <a name="language-support"></a>Prise en charge linguistique

La prise en charge linguistique de la reconnaissance vocale et de la reconnaissance vocale est disponible dans ces [langues prises en charge](create-a-phone-system-auto-attendant-languages.md).

Les commandes vocales suivantes sont disponibles pour la reconnaissance vocale :
  
|Commande vocale| Correspond à |
|:-----|:-----|
|Oui | Appuyez sur 1 pour Oui. |
|Non | Appuyez sur 2 pour Non. |
|Répéter |Répète la liste des options. Appuyez sur * sur le clavier pour répéter la liste des options. |
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

## <a name="related-topics"></a>Voir aussi

[Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
