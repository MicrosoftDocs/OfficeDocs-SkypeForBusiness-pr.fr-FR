---
title: Gestion de l’état d’Teams appareils
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: Cet article vous guide dans la gestion de l’état d’Teams des appareils sur Microsoft Teams installés sur ces appareils.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d5e98e65c35b8319a7e4f8675b68d530fa382c31
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984769"
---
# <a name="manage-the-health-of-teams-devices"></a>Gérer l’état d’Teams appareils

Les administrateurs peuvent surveiller l’état des appareils installés Microsoft Teams’aide de leur état d’état, ce qui indique la gravité des problèmes. Pour vérifier l’état d’un appareil, vous pouvez consulter la liste des appareils présente sous la **section** appareils Teams du Centre d’administration Teams’utilisateur. La colonne d’état d’état dans cette liste indique l’état d’état actuel de l’appareil. La sélection de ce statut ouvre le **panneau État** d’état d’santé, qui fournit des détails sur les problèmes d’état.

De nombreux types de problèmes peuvent contribuer à l’état d’état des appareils, et le système du centre d’administration Teams évalue la gravité de ces problèmes à mesure qu’ils se produisent.

L’administrateur qui gère Teams appareils pour leur organisation peut décider que la gravité des problèmes pour eux n’est pas identique à la configuration par défaut Teams fournit. Les administrateurs peuvent personnaliser la gravité et l’impact sur l’état de leurs appareils de façon à ce qu’ils correspondent aux priorités de leur organisation.

salles Teams périphériques sont connectés pour offrir une expérience de réunion complète, telle que Haut-parleur, Microphone, Affichage, Caméra. Des informations détaillées les concernant sont disponibles dans la page de l’appareil sous les onglets Périphériques et Santé. La connectivité de ces périphériques a un impact sur l’état du périphérique parent.

## <a name="feature-details"></a>Détails de la fonctionnalité

Lorsque vous affichez les détails périphériques sur une page d’un appareil, une option Gérer l’impact sur  **l’état d’santé** s’affiche. En outre, les administrateurs peuvent également voir l’impact de chaque périphérique sur l’état de l’appareil.

Par défaut, tous les périphériques ont un **impact critique sur** l’état de l’appareil. Si un périphérique est déconnecté, l’état  de l’appareil parent devient critique et ce problème s’affiche sous Problèmes **critiques** dans le panneau d’état d’état d’état.

> [!NOTE]
> Les catégories périphériques **HDMI ingest** et **Compute** ne sont pas disponibles pour la personnalisation, car elles sont essentielles au fonctionnement du dispositif parent.

## <a name="how-does-this-work"></a>Comment cela fonctionne-t-il ?

1. Un administrateur peut sélectionner les périphériques dont il souhaite modifier l’impact sur l’état d’état. Ils peuvent ensuite sélectionner Gérer **l’impact sur l’état d’santé.** Ils peuvent également trouver l’option Gérer **l’impact sur** l’état sous l’onglet **Périphériques** sur chaque carte périphérique.
1. Le **panneau d’impact** sur l’état d’santé s’ouvre, et l’administrateur peut sélectionner le niveau d’impact souhaité pour les périphériques sélectionnés et l’enregistrer.

| Paramètres Options | Description |
|------------------|-------------|
| **Non urgent** | Lorsqu’elle est définie pour une catégorie périphérique (par exemple, un affichage ou un **haut-parleur)** et que l’appareil est déconnecté, l’état d’état du périphérique salles Teams devient non urgent (au lieu de **Critique).** Les nouveaux problèmes seront classés dans la section **Non urgente** du panneau d’état d’état d’état.|
| **Aucun impact** | Lorsqu’elle est définie pour une catégorie périphérique et que le périphérique est déconnecté, l’état d’état du salles Teams reste sain **(au** lieu de **Critique).** Ce problème d’état d’santé ne s’affiche pas dans le panneau de statut d’état.|
| **Critique** | Lorsque la catégorie périphérique et le périphérique sont déconnectés, l’état d’état du salles Teams devient **critique.** Les nouveaux problèmes seront classés dans la **section** Critique du panneau d’état d’état d’état.|
| **Rétablir la valeur par défaut** | Lorsqu’elle est définie pour une catégorie périphérique, l’impact sur l’état de cette catégorie est redéfini sur **Critique.** Une fois ce choix enregistré, les modifications seront appliquées et l’impact sur l’état d’santé reflètera ces modifications à l’avenir.|

## <a name="applicable-device-categories"></a>Catégories d’appareils applicables

Actuellement, cette fonctionnalité est disponible pour gérer l’impact sur l’état des périphériques associés aux Salles Microsoft Teams (Windows).

## <a name="impact-on-other-workflows"></a>Impact sur les autres flux de travail

Si l’impact sur l’état des périphériques est moindre, les administrateurs peuvent ne pas remarquer de problèmes lorsqu’ils se produisent. Vous devez être attentif aux appareils à haute priorité qui ont besoin d’une surveillance étroite.

Par exemple, si une alerte est configurée pour être déclenchée pour confroom1 si son état devient **Critique.** L’administrateur a réduit l’impact sur l’affichage et le **haut-parleur** pour cette salle de réunion de la valeur par défaut **Critique** à Non urgent. Désormais, si l’affichage est déconnecté, l’état de la conférence ConfRoom1 **n’est pas urgent.** Dans ce cas, l’alerte ne sera pas déclenchée.
