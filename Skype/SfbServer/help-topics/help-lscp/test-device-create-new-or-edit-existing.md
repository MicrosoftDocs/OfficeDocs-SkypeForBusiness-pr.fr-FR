---
title: 'Périphérique de test : création d’un périphérique ou modification d’un périphérique existant'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La fonctionnalité Périphérique de test fonctionne en conjonction avec la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page Périphérique de test du Panneau de Skype Entreprise Server de contrôle.
ms.openlocfilehash: 1db9f9a7708bdad8ad94a4b24f9c0a40fadbdaade791fee41ecf9dd2deb98d4f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303916"
---
# <a name="test-device-create-new-or-edit-existing"></a>Test d’appareil : création d’un nouveau ou modification d’un test existant

La fonctionnalité Périphérique de test fonctionne en conjonction avec la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, il apparaît dans la liste de la page Périphérique de **test** du Panneau de Skype Entreprise Server de contrôle.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Nouveau périphérique de test** ou **Modifier le périphérique de test** :

- Ajouter un nouveau périphérique de test

- Modifier les propriétés d’un périphérique de test existant

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Étendue** Identifie l’étendue (globale ou site) du périphérique de test.

- **Nom** Vous pouvez ajouter ou modifier le nom du périphérique de test.

- **Nom de l’appareil** Vous pouvez ajouter ou modifier le nom du périphérique de test.

- **Type d’identificateur** Vous pouvez sélectionner la méthode à utiliser pour identifier l’appareil en sélectionnant l’une des méthodes suivantes :

  - **Adresse MAC**

  - **Numéro de série**

- **Identificateur unique** Vous pouvez taper l’adresse MAC ou le numéro de série de l’appareil.

Pour plus d’informations sur le test des périphériques, voir [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) dans la documentation des opérations.
## <a name="see-also"></a>Voir aussi

[Périphérique de test](test-device.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Afficher des mises à jour logicielles pour les périphériques dans votre entreprise](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)