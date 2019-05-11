---
title: Afficher les enregistrements d’utilisation PSTN dans Skype pour les entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Résumé : Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide de la Skype pour le panneau de configuration serveur Business ou le Skype pour Business Server Management Shell.'
ms.openlocfilehash: 933f20754aff5d8e8c9032cee02693e685130078
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892257"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Afficher les enregistrements d’utilisation PSTN dans Skype pour les entreprises

**Résumé :** Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide de la Skype pour le panneau de configuration serveur Business ou le Skype pour Business Server Management Shell.

Un enregistrement d’utilisation du réseau téléphonique commuté (RTC) spécifie une classe d’appel (interne, local ou longue distance) qui peut être utilisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation. Pour plus d’informations, reportez-vous à la rubrique [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) de la documentation de planification.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Pour afficher un enregistrement d’utilisation PSTN pour le panneau de configuration serveur Business à l’aide de Skype

1. Ouvrez le panneau de configuration serveur Business Skype.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation RTC**.

3. Dans la page **Utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

    > [!NOTE]
    > Une page en lecture seule de l’enregistrement d’utilisation RTC sélectionné affiche les itinéraires associés et les stratégies de voix associées.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Pour afficher les informations d’utilisation PSTN à l’aide de Skype pour les applets de commande Business Server Management Shell

- Pour afficher des informations sur toutes vos utilisations PSTN, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :

  ```
  Get-CsPstnUsage
  ```

    Cette commande renvoie le type d’informations suivant :

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Voir aussi

[Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises](voice-policy-and-pstn-usage-records.md)

