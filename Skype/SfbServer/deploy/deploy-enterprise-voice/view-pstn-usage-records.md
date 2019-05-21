---
title: Afficher les enregistrements d’utilisation RTC dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Résumé: Découvrez comment afficher les enregistrements d’utilisation de la Conférence RTC à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300922"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Afficher les enregistrements d’utilisation RTC dans Skype entreprise

**Résumé:** Découvrez comment afficher les enregistrements d’utilisation RTC à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.

Un enregistrement d’utilisation du réseau téléphonique commuté (RTC) spécifie une classe d’appel (interne, local ou longue distance) qui peut être utilisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation. Pour plus d’informations, reportez-vous à la rubrique [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) de la documentation de planification.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Pour afficher un enregistrement d’utilisation RTC en utilisant le panneau de configuration Skype entreprise Server

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation RTC**.

3. Dans la page **Utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

    > [!NOTE]
    > Une page en lecture seule de l’enregistrement d’utilisation RTC sélectionné affiche les itinéraires associés et les stratégies de voix associées.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Pour afficher les informations d’utilisation RTC à l’aide des applets de commande Skype entreprise Server Management Shell

- Pour afficher des informations sur l’ensemble de vos utilisations RTC, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:

  ```
  Get-CsPstnUsage
  ```

    Cette commande renvoie le type d’informations suivant :

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Voir aussi

[Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise](voice-policy-and-pstn-usage-records.md)

