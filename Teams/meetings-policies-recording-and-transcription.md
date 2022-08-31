---
title: Gérer les stratégies de réunion pour l’enregistrement et la transcription
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Apprenez à gérer les paramètres de stratégie de réunion dans Teams pour l’enregistrement et la transcription.
ms.openlocfilehash: 57e90984cde312f1804d5d2144c82a4d252822b6
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466202"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Paramètres de stratégie de réunion pour l’enregistrement & transcription

Cet article décrit les paramètres de stratégie de réunion spécifiques à l’enregistrement et à la transcription dans une réunion Teams. Ces paramètres se trouvent dans le Centre d’administration de l’équipe sous **Stratégies de réunions** > .

## <a name="transcription"></a>Transcription

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. La personne qui a lancé l'enregistrement doit activer ce paramètre pour que ces fonctionnalités fonctionnent avec son enregistrement.

L’activation de ce paramètre crée une copie de la transcription stockée avec l’enregistrement de la réunion, ce qui active **Recherche**, **CC** et **Transcriptions** sur l’enregistrement de réunion.

La transcription des réunions enregistrées est actuellement prise en charge uniquement pour les utilisateurs qui définissent leur langue ou parlent l’anglais dans les réunions Teams.

## <a name="cloud-recording"></a>Enregistrement cloud

Ce paramètre est une combinaison d’une stratégie par organisateur et par utilisateur et détermine si les réunions peuvent être enregistrées. L’enregistrement peut être démarré par l’organisateur de la réunion ou par un autre participant à la réunion si le paramètre de stratégie est activé pour le participant et s’il s’agit d’un utilisateur authentifié de la même organisation.

Les personnes extérieures à votre organisation, telles que les utilisateurs fédérés et anonymes, ne peuvent pas démarrer l’enregistrement. Les invités ne peuvent pas démarrer ou arrêter l’enregistrement.

![Capture d’écran montrant les options d’enregistrement](media/meeting-policies-recording.png)

Examinons l’exemple suivant.

| Utilisateur                 | Stratégie de réunion         | Autoriser l’enregistrement dans le Cloud |
|----------------------|------------------------|-----------------------|
| Daniela              | Global                 | Désactivé                   |
| Geneviève               | Location1MeetingPolicy | Activé                    |
| John (externe) | Non applicable         | Non applicable        |

- Les réunions organisées par Daniela ne peuvent pas être enregistrées.
- Amanda ne peut pas enregistrer les réuni ons organisées par Daniela.
- Les réunions organisées par Amanda peuvent être enregistrées.
- Daniela ne peut pas enregistrer les réuni ons organisées par Amanda.
- John ne peut pas enregistrer les réuni ons organisées par Amanda.

Pour en savoir plus sur l’enregistrement de réunions cloud, consultez [Enregistrement de réunion cloud Teams](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>Les réunions expirent automatiquement

Ce paramètre détermine si les enregistrements de réunion expirent automatiquement ou non. Après avoir activé ce paramètre, vous obtenez la possibilité de définir un délai d’expiration par défaut, mesuré en jours.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Capture d’écran du centre d’administration Teams du paramètre d’expiration automatique de la réunion.":::

Ce paramètre vous fournit un outil simple qui réduit la quantité de stockage utilisé pour les enregistrements plus anciens. Le système OneDrive et SharePoint surveillent le jeu d’expiration sur tous les enregistrements de réunion et déplacent automatiquement les enregistrements vers la corbeille à leur date d’expiration.

### <a name="default-expiration-time"></a>Délai d’expiration par défaut

Tous les enregistrements de réunion nouvellement créés auront une expiration par défaut de 120 jours ; tous les enregistrements créés une fois cette fonctionnalité activée seront supprimés 120 jours après leur date de création.

> [!NOTE]
> Le délai d’expiration par défaut maximal pour les utilisateurs A1 est de 30 jours.

#### <a name="changing-default-expiration-time"></a>Modification de l’heure d’expiration par défaut

Les administrateurs peuvent modifier le paramètre de délai d’expiration par défaut dans PowerShell ou le Centre d’administration Teams. Toutes les modifications n’affecteront que les enregistrements de réunion nouvellement créés à partir de ce point ; ils n’ont aucun impact sur les enregistrements créés avant cette date.

Les administrateurs ne peuvent pas modifier l’heure d’expiration des enregistrements de réunion existants. Cette opération est effectuée pour protéger la décision de l’utilisateur propriétaire de l’enregistrement. Les réunions et les appels peuvent être contrôlés par ce paramètre.

La valeur d’expiration est un entier pendant des jours.  Cette option peut être définie comme suit :

- Valeur minimale : **1**
- Valeur maximale : **99999**
- Vous pouvez également définir le délai d’expiration sur **-1** dans PowerShell afin que les enregistrements n’expirent jamais.

Exemple de commande PowerShell :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Conformité

Vous ne devez pas vous appuyer sur les paramètres d’expiration de la réunion pour la protection légale, car les utilisateurs finaux peuvent modifier la date d’expiration des enregistrements qu’ils contrôlent.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Enregistrement des paramètres d’expiration et des stratégies de rétention Microsoft 365 dans Microsoft Purview

La rétention des fichiers est prioritaire sur la suppression de fichier. Un enregistrement de réunion Teams avec une stratégie de rétention Purview ne peut pas être supprimé par une stratégie d’expiration d’enregistrement de réunion Teams tant que la période de rétention n’est pas terminée. Par exemple, si vous avez une stratégie de rétention Purview qui indique qu’un fichier sera conservé pendant cinq ans et qu’une stratégie d’expiration d’enregistrement de réunion Teams est définie pendant 60 jours, la stratégie d’expiration de l’enregistrement de réunion Teams supprime l’enregistrement après cinq ans.

Si vous disposez d’une stratégie d’expiration d’enregistrement de réunion Teams et d’une stratégie de suppression Purview avec des dates de suppression différentes, le fichier sera supprimé au plus tôt des deux dates. Par exemple, si vous disposez d’une stratégie de suppression Purview indiquant qu’un fichier sera supprimé après un an et qu’une date d’expiration de l’enregistrement de réunion Teams est définie pour 120 jours, la stratégie d’expiration de l’enregistrement de réunion Teams supprime le fichier après 120 jours.

Les utilisateurs peuvent supprimer manuellement leurs enregistrements avant la date d’expiration, sauf s’il existe une stratégie de rétention Purview qui l’empêche.

### <a name="deletion-of-recordings"></a>Suppression d’enregistrements

L’enregistrement est généralement supprimé dans un jour après la date d’expiration, mais dans de rares cas, il peut prendre jusqu’à cinq jours. Le propriétaire du fichier reçoit une notification par e-mail lorsque l’enregistrement expire et est dirigé vers la corbeille pour récupérer l’enregistrement.

> [!NOTE]
> À la date d’expiration, l’enregistrement est déplacé dans la corbeille et le champ date d’expiration est effacé. Si vous récupérez l’enregistrement à partir de la corbeille, il ne sera plus supprimé par cette fonctionnalité, car la date d’expiration a été effacée.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Expiration des enregistrements migrés à partir de Stream (Classic)

Les enregistrements migrés à partir de Stream (Classic) ne sont pas fournis avec un délai d’expiration défini. Au lieu de cela, nous encourageons les administrateurs à migrer uniquement les enregistrements qu’ils souhaitent conserver. Vous trouverez plus d’informations dans [la documentation sur la migration Stream (Classic)](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Stocker des enregistrements en dehors de votre pays ou région

Cette stratégie contrôle si les enregistrements de réunion peuvent être stockés définitivement dans un autre pays ou région. S’il est activé, les enregistrements ne peuvent pas être migrés. Pour plus d’informations sur les réunions cloud et l’emplacement de stockage des enregistrements, consultez [l’enregistrement des réunions cloud Teams](cloud-recording.md).

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)
- [Affecter des stratégies aux utilisateurs dans Teams](policy-assignment-overview.md)
- [Enregistrement de réunion cloud](cloud-recording.md)
- [Gérer les personnes autorisées à planifier des réunions](manage-who-can-schedule-meetings.md)
