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
description: Découvrez la fonctionnalité d’expiration de l’enregistrement de réunion dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67cbef7e6fad2c9620de17f89b8b3a4fe641368e
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853225"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Fonctionnalité d’expiration de l’enregistrement de réunion - Forum aux questions

**Quelle est la modification ?**

Nous introduisons un paramètre d’expiration de 120 jours par défaut pour *tous les* enregistrements de réunion de Teams nouvellement créés . Cette option est activée par défaut pour tous les locataires et vous devez la désactiver si vous ne souhaitez pas cette fonctionnalité. Le système OneDrive et SharePoint surveille la date d’expiration définie sur tous les TMR et déplace automatiquement les TMR vers la corbeille à leur date d’expiration.

**Pourquoi introduisons-nous ce changement ?**

Nous avons répondu à vos demandes pour la fonctionnalité d’expiration de l’enregistrement de la réunion. Il s’agit d’un mécanisme de nettoyage léger pour réduire l’encombrement du stockage créé à partir de TMR froid. En moyenne, 99 % des TMR ne sont jamais réexécuter après 120 jours.

**Pourquoi cette option est-elle activée par défaut ?**

Nous pensons que presque tous les clients bénéficieront de la réduction de la charge de stockage sur leur locataire en supprimant les enregistrements qui ne seront probablement jamais réexécuter après 120 jours. Notre objectif est de fournir une expérience aussi propre que possible à tous les clients par défaut.

**Comment la date d’expiration est-elle calculée ?**

La date d’expiration est calculée en tant que jour de création, plus le nombre de jours par défaut défini dans la stratégie de Teams par l’administrateur.

**Comment un administrateur peut-il modifier la date d’expiration ?**

Les administrateurs peuvent modifier le paramètre d’expiration par défaut dans leur console de stratégie Teams. Ce changement n’affectera que les tmrs nouvellement créés à partir de ce point. Il n’aura aucun impact sur les enregistrements antérieurs à cette date.

Les administrateurs ne peuvent pas modifier la date d’expiration sur les TMR existants. Cette opération est effectuée pour protéger la décision de l’utilisateur propriétaire du TMR.

**Qui cela a-t-il un impact ?**

Toute personne qui stocke des TMR dans OneDrive ou SharePoint.

**Pourquoi dois-je utiliser cette fonctionnalité ?**

Cette fonctionnalité est activée par défaut. Pour le désactiver, remplacez le paramètre d’expiration par défaut de la console de stratégie Teams par **« Aucune expiration** ».
Vous devez l’utiliser pour limiter la consommation de stockage OneDrive ou Sharepoint for Cloud pilotée par Teams enregistrements de réunion. Un enregistrement de réunion classique consomme environ 400 Mo par heure d’enregistrement.

**Dois-je m’appuyer sur cette fonctionnalité pour un respect strict de la sécurité et de la conformité ?**

Non, vous ne devez pas vous fier à cela pour la protection légale, car les utilisateurs finaux peuvent modifier la date d’expiration des enregistrements qu’ils contrôlent.

**Une stratégie de rétention et/ou de suppression que j’ai définie dans le Centre de sécurité & conformité remplacera-t-elle le paramètre d’expiration de l’enregistrement de la réunion Teams ?**

Oui, toutes les stratégies que vous avez définies dans le centre de conformité sont prioritaires.

Par exemple :

- Si vous disposez d’une stratégie indiquant que tous les fichiers d’un site doivent être conservés pendant 100 jours et que le paramètre d’expiration d’un enregistrement de réunion Teams est de 30 jours, l’enregistrement est conservé pendant les 100 jours complets.
- Si vous avez une stratégie de suppression indiquant que tous les enregistrements de réunion Teams seront supprimés après cinq jours et que vous disposez d’un paramètre d’expiration pour un enregistrement de réunion Teams de 30 jours, l’enregistrement sera supprimé après cinq jours.

**Que se passe-t-il lorsqu’un TMR expire ?**

À la date d’expiration, l’enregistrement est déplacé dans la corbeille et le champ date d’expiration est effacé. Si vous récupérez l’enregistrement à partir de la corbeille, il ne sera plus supprimé par cette fonctionnalité, car la date d’expiration a été effacée.

**Comment être averti de l’expiration d’un fichier ?**

- Tout le monde verra une notification concernant la date d’expiration dans la liste de vérification de l’enregistrement dans la fenêtre de conversation Teams.
- Toutes les personnes ayant accès à l’affichage verront une icône rouge en regard du fichier dans votre dossier OneDrive ou SharePoint 14 jours avant l’expiration du fichier.
- Le propriétaire du fichier reçoit une notification par e-mail lorsque l’enregistrement expire et est dirigé vers la corbeille pour récupérer l’enregistrement.

**Quelles sont les références SKU requises pour cette fonctionnalité ?**

- Toutes les références SKU auront cette fonctionnalité par défaut.

- Les utilisateurs A1 ont par défaut une période d’expiration de 30 jours et ne peuvent pas modifier la date d’expiration.

**L’expiration du fichier est-elle un événement audité et puis-je le voir dans mes journaux d’audit ?**

Oui, ceux-ci s’affichent en tant qu’événements de suppression système dans le journal d’audit.

**Que se passe-t-il si je veux que l’administrateur ait un contrôle total sur le cycle de vie des enregistrements de réunion et ne souhaite pas donner aux utilisateurs finaux la possibilité de remplacer la date d’expiration ?**

Nous vous recommandons d’utiliser les stratégies de conservation et/ou de suppression de sécurité et/ou de suppression disponibles dans le cadre de la référence SKU de conformité E5. Cette offre vise à résoudre des problèmes juridiques d’administration complexes basés sur des stratégies et des contrats SLA.

Cette fonctionnalité est uniquement conçue comme un mécanisme de nettoyage léger pour réduire l’encombrement du stockage créé à partir d’enregistrements de réunions Teams froids.

**Quand le fichier sera-t-il supprimé ?**

Le fichier sera supprimé dans les cinq jours suivant la date d’expiration, bien qu’il ne s’agit pas d’une garantie stricte.

**L’expiration par défaut est de 120 jours, mais quand j’ai vérifié Teams centre d’administration, c’est 60 jours. Pourquoi?**

La façon dont les stratégies Teams fonctionnent est si une stratégie dans le centre est définie par l’administrateur, un instantané mis en cache est pris de tous les paramètres. Si l’administrateur a défini un attribut sur la stratégie lorsque nous avions temporairement une valeur par défaut de 60 jours, il devra le modifier manuellement à 120 jours. S’ils n’ont pas de paramètre personnalisé avant que nous définissions la valeur par défaut de 120 jours, ils obtiennent les 120 jours.
