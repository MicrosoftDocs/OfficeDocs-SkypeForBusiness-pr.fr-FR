---
title: Fonctionnalité d’expiration de l’enregistrement de réunion
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: En savoir plus sur la fonctionnalité d’expiration de l’enregistrement de la réunion Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889524"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Fonctionnalité d’expiration de l’enregistrement de réunion - Questions fréquemment posées

**Quelle est la modification ?**

Nous présentons un paramètre d’expiration de  60 jours par défaut pour tous les enregistrements de réunion nouvellement Teams (TMR). Cette option est par défaut pour tous les locataires et vous devez la désactiver si vous ne souhaitez pas cette fonctionnalité. Le OneDrive et SharePoint de contrôle des détails des tmrs surveille la date d’expiration définie sur toutes les tmR et déplace automatiquement les tmR vers la Corbeille à la date d’expiration.

**Pourquoi introduisons-nous ce changement ?**

Nous avons répondu à vos demandes pour la fonctionnalité d’expiration de l’enregistrement de la réunion. Il s’agit d’un mécanisme de tâches légères permettant de réduire l’encombrement du stockage créé par la tmR froide. En moyenne, 99 % des tmR ne sont jamais re chronomètres après 60 jours.

**Pourquoi cette option est-elle activée par défaut ?**

Nous pensons que presque tous les clients tireront parti de la charge de stockage réduite sur leur locataire en supprimant les enregistrements qui ne seront probablement jamais revus après 60 jours. Notre objectif est d’offrir par défaut une expérience aussi propre que possible à tous les clients.

**Comment la date d’expiration est-elle calculée ?**

La date d’expiration est calculée en tant que jour de création, ainsi que le nombre de jours par défaut Teams la stratégie par l’administrateur.

**Comment un administrateur peut-il modifier la date d’expiration ?**

Les administrateurs peuvent modifier le paramètre d’expiration par défaut dans leur console Teams stratégie. Cette modification n’affectera que les personnes qui viennent d’être créées à partir de ce point. Aucun enregistrement enregistré avant cette date n’est impacté.

Les administrateurs ne peuvent pas modifier la date d’expiration des tmrs existants. Cela permet de protéger la décision de l’utilisateur propriétaire de la tmR.

**Quel est l’impact de cette situation ?**

Toute personne stockant des tmRs dans OneDrive ou SharePoint.

**Pourquoi dois-je utiliser cette fonctionnalité ?**

Cette fonctionnalité est en cours d’option par défaut. Pour le désactiver, modifiez le paramètre d’expiration par défaut de la console Teams de stratégie à **Aucune date d’expiration.**
Vous devez l’utiliser pour limiter la consommation de stockage cloud OneDrive sharepoint, pilotée par Teams enregistrements de réunion. L’enregistrement d’une réunion ordinaire consomme environ 400 Mo par heure d’enregistrement.

**Dois-je m’appuyer sur cette fonctionnalité pour respecter strictement la sécurité et la conformité ?**

Non, vous ne devez pas vous baser sur cette protection juridique, car les utilisateurs finaux peuvent modifier la date d’expiration de tous les enregistrements qu’ils contrôlent.

**Une stratégie de rétention et/ou de suppression définie dans le Centre de sécurité et conformité & remplace-t-elle le paramètre d’expiration de l’enregistrement Teams réunion ?**

Oui, toutes les stratégies que vous avez définies dans le Centre de conformité sont prioritaire.

Par exemple :

- Si vous avez une stratégie qui indique que tous les fichiers d’un site doivent être conservés pendant 100 jours et que le paramètre d’expiration pour un enregistrement de réunion Teams est de 30 jours, l’enregistrement est conservé pendant 100 jours.
- Si vous avez une stratégie de suppression qui indique que tous les enregistrements de réunion Teams seront supprimés au bout de cinq jours et que vous avez un paramètre d’expiration pour un enregistrement de réunion Teams de 30 jours, l’enregistrement sera supprimé au bout de cinq jours.

**Que se passe-t-il lorsqu’une tmR arrive à expiration ?**

À la date d’expiration, l’enregistrement est déplacé vers la Corbeille et le champ de date d’expiration est effacé. Si vous récupérez l’enregistrement à partir de la Corbeille, il ne sera pas supprimé de nouveau par cette fonctionnalité, car la date d’expiration a été effacée.

**Comment être averti de l’expiration d’un fichier ?**

- Tout le monde voit une notification concernant la date d’expiration dans la liste de vérification de l’enregistrement dans la Teams conversation.
- Toutes les personnes ayant accès à l’affichage verront une icône rouge en regard du fichier dans votre dossier OneDrive ou SharePoint 14 jours avant l’expiration du fichier.
- Le propriétaire du fichier recevra une notification par e-mail à l’expiration de l’enregistrement et sera dirigé vers la Corbeille pour récupérer l’enregistrement.

**Quelles sont les références SKU requises pour cette fonctionnalité ?**

- Toutes les références SKU auront cette fonctionnalité par défaut.

- Par défaut, tous les utilisateurs ont une période d’expiration de 30 jours et ne peuvent pas modifier la date d’expiration.

**L’expiration du fichier est-elle un événement audité et puis-je le voir dans mes journaux d’audit ?**

Oui, ces événements s’afficheront sous la mesure d’événements de suppression système dans le journal d’audit.

**Que faire si je souhaite que l’administrateur contrôle entièrement le cycle de vie des enregistrements des réunions et que je ne souhaite pas donner aux utilisateurs finaux la possibilité de remplacer la date d’expiration ?**

Nous vous recommandons d’utiliser les stratégies de rétention et/ou de suppression de sécurité et/ou de suppression disponibles dans le cadre de la référence SKU de conformité E5. Cette offre vise à résoudre des problèmes juridiques d’administration complexes basés sur des stratégies et des contrats SLA.

Cette fonctionnalité est uniquement destinée à un mécanisme léger de gestion des tâches afin de réduire l’encombrement du stockage créé à partir Teams les enregistrements des réunions.

**Quand le fichier sera-t-il supprimé ?**

Le fichier sera supprimé dans les cinq jours suivant la date d’expiration, même si ce n’est pas une garantie stricte.
