---
title: Périphérique de test
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier la fonctionnalité des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page Périphérique de test du Panneau de Skype Entreprise Server de contrôle.
ms.openlocfilehash: 96e9c12444293f6fa7aa0c12f538fae0241474d3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748060"
---
# <a name="test-device"></a>Test d’appareil

Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier la fonctionnalité des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, il apparaît dans la liste de la page Périphérique de **test** du Panneau de Skype Entreprise Server de contrôle.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Périphérique de test** :

- Ajouter un périphérique de test globalement ou pour un site particulier

- Modifier les options pour un périphérique de test existant

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Nouveau** Vous pouvez ajouter un nouveau périphérique de test avec l’étendue suivante :

  - Global

  - Site

- **Modifier** Vous pouvez modifier les options d’un périphérique de test dans la liste. À l’aide de cette option, vous pouvez effectuer les opérations suivantes :

  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’un périphérique de test.

  - **Sélectionner tout** Cette option sélectionne tous les périphériques de test dans la liste.

  - **Supprimer** Cette option supprime tous les périphériques de test sélectionnés.

- **Actualiser** Vous pouvez actualiser la liste des périphériques de test pour vérifier l’état des options de tous les périphériques de test.

Pour plus d’informations sur le test des périphériques, voir [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) dans la documentation des opérations.
## <a name="see-also"></a>Voir aussi

[Périphérique de test : création d’un périphérique ou modification d’un périphérique existant](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Afficher des mises à jour logicielles pour les périphériques dans votre entreprise](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)