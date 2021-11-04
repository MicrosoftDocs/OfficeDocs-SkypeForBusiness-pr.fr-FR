---
title: Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Résumé : Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: 2b09ed19de6ff205ee7d76e7379c8b4c5fc12d06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771519"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise

**Résumé :** Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.

Un enregistrement d’utilisation du réseau téléphonique commuté (PSTN) spécifie une classe d’appel (interne, local ou longue distance) qui peut être réalisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation. Pour plus d’informations, voir [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) dans la documentation de planification.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Pour afficher un enregistrement d’utilisation PSTN à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation PSTN**.

3. Dans la page **Utilisation PSTN**, sélectionnez l’enregistrement d’utilisation PSTN que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

    > [!NOTE]
    > Une page en lecture seule de l’enregistrement d’utilisation PSTN sélectionné affiche les itinéraires associés et les stratégies de voix associées.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Pour afficher les informations d’utilisation PSTN à l’aide des cmdlets Skype Entreprise Server Management Shell

- Pour afficher des informations sur toutes vos utilisations PSTN, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :

  ```powershell
  Get-CsPstnUsage
  ```

    Cette commande renvoie des informations comme celles-ci :

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Voir aussi

[Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise](voice-policy-and-pstn-usage-records.md)