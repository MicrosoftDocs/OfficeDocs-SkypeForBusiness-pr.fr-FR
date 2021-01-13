---
title: Unassigned Phone Number Create New or Edit Existing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: a584812b32d99796259bde56838f0193c54b8fac
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812094"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numéro de téléphone non attribué : créer un nouveau ou modifier un numéro existant

> [!NOTE]
> La messagerie un utilisateur Exchange reste disponible dans Skype Entreprise Server 2019 lorsque vous intégrez Skype Entreprise 2019 à Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie un Standard automatique Cloud est mise en avant.

Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.

> [!IMPORTANT]
> Lorsque vous avez terminé de créer une nouvelle plage de numéros non affectés ou d’en modifier une existante, cliquez sur **OK** pour retourner à la page **Numéro non attribué** qui répertorie toutes les plages de numéros. Les modifications que vous avez apportées dans la page **Nouvelle plage de numéros non attribués** et la page **Modifier la plage de numéros non attribués** sont validées dans la base de données seulement lorsque vous cliquez sur **Valider tout** dans la page **Numéro non attribué**.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Nom** Tapez un nom descriptif qui identifie la plage de numéro non assignés. Une fois que vous avez enregistrez la plage, ce nom ne peut pas être modifié.

- **Plage de nombres** Dans le premier champ, tapez le numéro de début de la plage de numéro non assignés. Dans le deuxième champ, tapez le numéro de fin de la plage.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin.

  - Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.

  - Le numéro doit correspondre à l’expression régulière (tel:)?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. Cela signifie que le numéro peut commencer par la chaîne tel: (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre de 1 à 9. Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.

- **Service d’annonce** Sélectionnez **Annonce** pour que l’application Annonce gère l’appel entrant ou la um **Exchange** pour qu’une Standard automatique exchange gère l’appel entrant.

- Si vous avez sélectionné **Annonce** comme **Service d’annonce** :

  - **FQDN du serveur de destination** Sélectionnez l’ID de service du service d’application qui exécute l’application d’annonce qui gérera les appels entrants vers cette plage de numéros non assignés.

  - **Annonce** Sélectionnez l’annonce à lire pour cette plage de numéros non assignés.

- Si vous avez sélectionné **Messagerie unifiée Exchange** comme **Service d’annonce** :

  - **Standard automatique numéro de téléphone** Sélectionnez le numéro de téléphone de la Standard automatique de la Standard automatique.

Pour plus d’informations sur les fonctionnalités d’annonce, voir [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation. Pour plus d’informations sur l’utilisation de plages de numéros non attribués, voir [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) dans la documentation des opérations.


