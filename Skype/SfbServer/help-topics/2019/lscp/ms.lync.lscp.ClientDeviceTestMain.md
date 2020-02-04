---
title: Périphérique de test
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un périphérique globalement (dans tout votre environnement) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page périphérique de test du panneau de configuration Skype entreprise Server.
ms.openlocfilehash: f9a512c2546dcef3865e2d8b75ecf2f05c0c9db9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705159"
---
# <a name="test-device"></a>Périphérique de test

Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un périphérique globalement (dans tout votre environnement) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page **périphérique de test** du panneau de configuration Skype entreprise Server.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page de test de l' **appareil** :

- Ajouter un appareil de test globalement ou pour un site particulier.

- Modifiez les options pour un appareil de test existant.

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Nouvelle** Vous pouvez ajouter un nouvel appareil de test avec l’étendue suivante :

  - Globale

  - Site

- **Modifier** Vous pouvez modifier les options d’un périphérique de test dans la liste. Cette option vous permet d’effectuer les opérations suivantes :

  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour un appareil de test.

  - **Tout sélectionner** Cette option sélectionne tous les appareils de test dans la liste.

  - **Supprimer** Cette option supprime tous les périphériques de test sélectionnés.

- **Actualiser** Vous pouvez actualiser la liste de périphériques de test pour vérifier l’état des options de tous les appareils de test.

Pour plus d’informations sur le test des périphériques, reportez-vous à la rubrique [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) de la documentation des opérations.
## <a name="see-also"></a>Voir aussi

[Périphérique de test : création d’un périphérique ou modification d’un périphérique existant](ms.lync.lscp.ClientDeviceTestEdit.md)

[Nouveau-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Afficher les mises à jour logicielles des appareils de votre organisation](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
