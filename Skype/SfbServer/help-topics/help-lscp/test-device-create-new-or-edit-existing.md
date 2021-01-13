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
description: La fonctionnalité Périphérique de test fonctionne en conjonction avec la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page Périphérique de test du Panneau de contrôle Skype Entreprise Server.
ms.openlocfilehash: cf4895e84e486939515094042010383854587f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819064"
---
# <a name="test-device-create-new-or-edit-existing"></a>Test d’appareil : création d’un nouveau ou modification d’un test existant

La fonctionnalité Périphérique de test fonctionne en conjonction avec la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page Périphérique de **test** du Panneau de contrôle Skype Entreprise Server.

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

Pour plus d’informations sur le test des périphériques, voir [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) dans la documentation des opérations.
## <a name="see-also"></a>Voir aussi

[Périphérique de test](test-device.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Afficher des mises à jour logicielles pour les périphériques dans votre entreprise](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
