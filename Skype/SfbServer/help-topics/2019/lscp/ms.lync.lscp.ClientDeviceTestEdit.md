---
title: Test de création ou de modification d’un périphérique existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: La fonctionnalité Périphérique de test fonctionne conjointement à la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un périphérique globalement (dans tout votre environnement) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page périphérique de test du panneau de configuration Skype entreprise Server.
ms.openlocfilehash: f869669a657997a4d020c2dc54015bd16a5f9443
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691549"
---
# <a name="test-device-create-new-or-edit-existing"></a>Périphérique de test : création d’un périphérique ou modification d’un périphérique existant

La fonctionnalité Périphérique de test fonctionne conjointement à la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un périphérique globalement (dans tout votre environnement) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page **périphérique de test** du panneau de configuration Skype entreprise Server.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouveau périphérique de test** ou **Modifier le périphérique de test**, vous pouvez effectuer les tâches suivantes :

- Ajout d’un nouveau périphérique de test

- Modification des propriétés d’un périphérique de test existant

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Scope** Identifie l’étendue (globale ou site) de l’appareil de test.

- **Nom** Vous pouvez ajouter ou modifier le nom de l’appareil de test.

- **Nom** de l’appareil Vous pouvez ajouter ou modifier le nom de l’appareil de test.

- **Type d’identificateur** Vous pouvez sélectionner la méthode à utiliser pour identifier l’appareil en sélectionnant l’une des options suivantes :

  - **Adresse MAC**

  - **Numéro de série**

- **Identificateur unique** Vous pouvez entrer l’adresse MAC ou le numéro de série de l’appareil.

Pour plus d’informations sur le test des périphériques, reportez-vous à la rubrique [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) de la documentation des opérations.
## <a name="see-also"></a>Voir aussi

[Périphérique de test](ms.lync.lscp.ClientDeviceTestMain.md)

[Nouveau-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Afficher les mises à jour logicielles des appareils de votre organisation](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
