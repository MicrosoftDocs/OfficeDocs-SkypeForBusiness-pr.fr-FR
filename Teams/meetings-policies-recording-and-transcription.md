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
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams pour l’enregistrement et la transcription.
ms.openlocfilehash: fd0dc824f380fb9a001442267445340944e055c4
ms.sourcegitcommit: 2d1bb69e0d6bc35be0b57c7c5d87f58ab013dafb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "68928310"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Paramètres de stratégie de réunion pour l’enregistrement & la transcription

Cet article décrit les paramètres de stratégie de réunion spécifiques à l’enregistrement et à la transcription dans une réunion Teams. Ces paramètres se trouvent dans le Centre d’administration d’équipe sous **Réunions** > **Stratégies de réunion**.

## <a name="transcription"></a>Transcription

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. La personne qui a lancé l'enregistrement doit activer ce paramètre pour que ces fonctionnalités fonctionnent avec son enregistrement.

L’activation de ce paramètre crée une copie de la transcription stockée avec l’enregistrement de la réunion, ce qui active **Recherche**, **CC** et **Transcriptions** sur l’enregistrement de réunion.

## <a name="cloud-recording"></a>Enregistrement cloud

Ce paramètre est une combinaison d’une stratégie par organisateur et par utilisateur et contrôle si les réunions peuvent être enregistrées. L’enregistrement peut être démarré par l’organisateur de la réunion ou par un autre participant à la réunion si le paramètre de stratégie est activé pour le participant et s’il s’agit d’un utilisateur authentifié de la même organisation.

Les personnes extérieures à votre organisation, telles que les utilisateurs fédérés et anonymes, ne peuvent pas démarrer l’enregistrement. Les invités ne peuvent pas démarrer ou arrêter l’enregistrement.

![Capture d’écran montrant les options d’enregistrement](media/meeting-policies-recording.png)

Examinons l’exemple suivant.

| Utilisateur                 | Stratégie de réunion         | Autoriser l’enregistrement dans le Cloud |
|----------------------|------------------------|-----------------------|
| Daniela              | Global                 | Désactivé                   |
| Geneviève               | Location1MeetingPolicy | Activé                    |
| John (externe) | Non applicable         | Non applicable        |

- Les réunions organisées par Daniela ne peuvent pas être enregistrées.
- Amanda ne peut pas enregistrer les réunions organisées par Daniela.
- Les réunions organisées par Amanda peuvent être enregistrées.
- Daniela ne peut pas enregistrer les réunions organisées par Amanda.
- John ne peut pas enregistrer les réunions organisées par Amanda.

Pour en savoir plus sur l’enregistrement de réunions cloud, consultez [Enregistrement de réunion cloud Teams](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>Les réunions expirent automatiquement

Ce paramètre contrôle si les enregistrements de réunion expirent automatiquement ou non. Après avoir activé ce paramètre, vous avez la possibilité de définir un délai d’expiration par défaut, mesuré en jours.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Capture d’écran du centre d’administration Teams du paramètre d’expiration automatique de réunion.":::

Ce paramètre vous fournit un outil simple qui réduit la quantité de stockage d’enregistrements plus anciens utilisés. Le système OneDrive et SharePoint surveille l’expiration définie sur tous les enregistrements de réunion et déplace automatiquement les enregistrements vers la corbeille à leur date d’expiration.

### <a name="default-expiration-time"></a>Délai d’expiration par défaut

Tous les enregistrements de réunion nouvellement créés ont une expiration par défaut de 120 jours. tous les enregistrements créés après l’activation de cette fonctionnalité seront supprimés 120 jours après leur date de création.

> [!NOTE]
> Le délai d’expiration maximal par défaut pour les utilisateurs A1 est de 30 jours.

#### <a name="changing-default-expiration-time"></a>Modification de l’heure d’expiration par défaut

Les administrateurs peuvent modifier le paramètre Délai d’expiration par défaut dans PowerShell ou le Centre d’administration Teams. Les modifications n’affecteront que les enregistrements de réunion nouvellement créés à partir de ce point; elles n’auront aucun impact sur les enregistrements créés avant cette date.

Les administrateurs ne peuvent pas modifier l’heure d’expiration des enregistrements de réunion existants. Cette opération est effectuée pour protéger la décision de l’utilisateur propriétaire de l’enregistrement. Les réunions et les appels peuvent être contrôlés par ce paramètre.

La valeur d’expiration est un entier pour les jours.  Cela peut être défini comme suit :

- Valeur minimale : **1**
- Valeur maximale : **99999**
- Vous pouvez également définir l’heure d’expiration sur **-1** dans PowerShell afin que les enregistrements n’expirent jamais.

Exemple de commande PowerShell :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Conformité

Vous ne devez pas vous appuyer sur les paramètres d’expiration de réunion pour la protection juridique, car les utilisateurs finaux peuvent modifier la date d’expiration des enregistrements qu’ils contrôlent.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Enregistrement des paramètres d’expiration et des stratégies de rétention Microsoft 365 dans Microsoft Purview

La conservation des fichiers est prioritaire sur la suppression de fichier. Un enregistrement de réunion Teams avec une stratégie de rétention Purview ne peut pas être supprimé par une stratégie d’expiration d’enregistrement de réunion Teams tant que la période de rétention n’est pas terminée. Par exemple, si vous avez une stratégie de rétention Purview qui indique qu’un fichier sera conservé pendant cinq ans et qu’une stratégie d’expiration d’enregistrement de réunion Teams définie sur 60 jours, la stratégie d’expiration de l’enregistrement des réunions Teams supprimera l’enregistrement après cinq ans.

Si vous avez une stratégie d’expiration d’enregistrement de réunion Teams et une stratégie de suppression Purview avec des dates de suppression différentes, le fichier est supprimé au plus tôt des deux dates. Par exemple, si vous avez une stratégie de suppression Purview qui indique qu’un fichier sera supprimé après un an et qu’une date d’expiration d’enregistrement de réunion Teams est définie sur 120 jours, la stratégie d’expiration de l’enregistrement des réunions Teams supprime le fichier après 120 jours.

Les utilisateurs peuvent supprimer manuellement leurs enregistrements avant la date d’expiration, sauf si une stratégie de rétention Purview l’empêche.

### <a name="deletion-of-recordings"></a>Suppression des enregistrements

L’enregistrement est généralement supprimé dans le jour suivant la date d’expiration, mais dans de rares cas, il peut prendre jusqu’à cinq jours. Le propriétaire du fichier reçoit une notification par e-mail à l’expiration de l’enregistrement et est dirigé vers la Corbeille pour récupérer l’enregistrement.

> [!NOTE]
> À la date d’expiration, l’enregistrement est déplacé dans la corbeille et le champ date d’expiration est effacé. Si vous récupérez l’enregistrement à partir de la corbeille, cette fonctionnalité ne le supprimera plus, car la date d’expiration a été effacée.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Expiration des enregistrements migrés à partir de Stream (Classic)

Les enregistrements migrés à partir de Stream (Classic) ne sont pas fournis avec une date d’expiration définie sur eux. Au lieu de cela, nous encourageons les administrateurs à migrer uniquement les enregistrements qu’ils souhaitent conserver. Pour plus d’informations, consultez [la documentation sur la migration Stream (Classic)](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Stocker des enregistrements en dehors de votre pays ou région

Cette stratégie contrôle si les enregistrements de réunion peuvent être stockés de manière permanente dans un autre pays ou une autre région. S’il est activé, les enregistrements ne peuvent pas être migrés. Pour plus d’informations sur les réunions cloud et l’emplacement où les enregistrements sont stockés, consultez [Enregistrement des réunions cloud Teams](cloud-recording.md).

## <a name="related-topics"></a>Rubriques connexes

- [Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)
- [Affecter des stratégies aux utilisateurs dans Teams](policy-assignment-overview.md)
- [Enregistrement de réunion cloud](cloud-recording.md)
- [Gérer les personnes autorisées à planifier des réunions](manage-who-can-schedule-meetings.md)
