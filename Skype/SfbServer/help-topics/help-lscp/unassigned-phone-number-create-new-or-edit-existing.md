---
title: Numéro d’Téléphone non Téléphone création d’un numéro ou modification d’un numéro existant
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 13b2caaa8e7b364fa60ab32e6c62f982612121c4861197cd2b76597975c0ba50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313392"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numéro de téléphone non attribué : créer un nouveau ou modifier un numéro existant

Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.

> [!IMPORTANT]
> Lorsque vous avez terminé de créer une nouvelle plage de numéros non affectés ou d’en modifier une existante, cliquez sur **OK** pour retourner à la page **Numéro non attribué** qui répertorie toutes les plages de numéros. Les modifications que vous avez apportées dans la page **Nouvelle plage de numéros non attribués** et la page **Modifier la plage de numéros non attribués** sont validées dans la base de données seulement lorsque vous cliquez sur **Valider tout** dans la page **Numéro non attribué**.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Nom** Tapez un nom descriptif qui identifie la plage de numéro non assignés. Une fois que vous avez enregistrez la plage, ce nom ne peut pas être modifié.

- **Plage de nombres** Dans le premier champ, tapez le numéro de début de la plage de numéro non assignés. Dans le deuxième champ, tapez le numéro de fin de la plage.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin.

  - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.

  - Le nombre doit correspondre à l’expression régulière `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` . Cela signifie que le numéro peut commencer par la chaîne (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre de 1 à `tel:` 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.

- **Service d’annonce** Sélectionnez **Annonce** pour que l’application Annonce gère l’appel entrant ou la Exchange **pour** qu’une Exchange de Standard automatique l’appel entrant.

- Si vous avez sélectionné **Annonce** comme **Service d’annonce** :

  - **FQDN du serveur de destination** Sélectionnez l’ID de service du service d’application qui exécute l’application d’annonce qui gérera les appels entrants vers cette plage de numéros non assignés.

  - **Annonce** Sélectionnez l’annonce à lire pour cette plage de numéros non signés.

- Si vous avez sélectionné **Messagerie unifiée Exchange** comme **Service d’annonce** :

  - **Standard automatique numéro de téléphone** Sélectionnez le numéro de téléphone de la Exchange de Standard automatique.

Pour plus d’informations sur les fonctionnalités d’annonce, voir [Plan for the Announcement application in Skype Entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation. Pour plus d’informations sur l’utilisation de plages de numéros non attribués, voir [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) dans la documentation des opérations.