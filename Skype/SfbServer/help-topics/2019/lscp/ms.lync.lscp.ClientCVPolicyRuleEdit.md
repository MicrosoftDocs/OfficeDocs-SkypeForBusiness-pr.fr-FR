---
title: Règle de version du client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.
ms.openlocfilehash: a4d8cb38f30e8c332a9cec0ea90e27c012187d47
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794593"
---
# <a name="client-version-rule"></a>Règle de version du client

Une stratégie de version de client est composée d’un ensemble de règles de version de client. Ces règles définissent les actions qui doivent être effectuées lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :

- Ajout de nouvelles règles à une stratégie de version de client

- Modification des règles composant une stratégie de version de client existante

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Agent utilisateur** Vous pouvez sélectionner un type de client dans la liste. Le tableau suivant définit les codes des agents utilisateurs. Cette liste comprend les types de clients hérités, qui ne sont plus pris en charge.

|**Nom du client**|**Agent utilisateur**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, téléphone Office Communicator  <br/> |OCPhone  <br/> |
|Communicator Phone Edition Platform  <br/> |CPE  <br/> |
|Unified Communications Platform  <br/> |UCCP  <br/> |
|Lync 2010 participant  <br/> |AOC  <br/> |
|Complément Live Meeting  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client Real-time Communications  <br/> |RTC  <br/> |
|Lync 2010 pour iPad  <br/> |iPadLync  <br/> |
|Lync 2010 pour iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 pour Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 pour Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 pour Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants ou utiliser des caractères génériques pour indiquer le numéro de version du client.

  - **Version principale** Spécifie le numéro qui correspond à la version majeure du client.

  - **Version mineure** Spécifie le numéro qui correspond à la version mineure du client.

  - **Créer** Spécifie le numéro de build qui correspond à la version majeure et mineure du client.

  - **Mise à jour** Spécifie le numéro qui correspond à la version mise à jour du client.

- **Opération de comparaison** Vous pouvez spécifier l’opération correspondante pour la version du client spécifiée dans les étapes précédentes. Les opérations suivantes sont disponibles :

  - **Identique à**

  - **Différent de**

  - **Antérieur à**

  - **Antérieur ou simultané**

  - **Postérieur à**

  - **Postérieur ou simultané**

- **Action** Vous pouvez spécifier l’action à exécuter lorsque les critères spécifiés dans les étapes précédentes sont remplis. Les actions suivantes sont disponibles :

  - **Autoriser** Permet au client de se connecter.

  - **Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update. Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .

    > [!NOTE]
    > La sélection de cette action entraîne l’affichage d’une notification lors de la prochaine connexion de l’utilisateur à Skype entreprise. La notification indique qu’une mise à jour est disponible, même si des mises à jour n’ont pas encore été publiées dans Windows Server Update service ou Microsoft Update. Pour éviter toute confusion, ne sélectionnez cette action qu’après que les mises à jour sont disponibles.

  - **Allow with URL** Permet au client de se connecter et d’afficher un message permettant de télécharger une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.

  - **Bloquer** Empêche le client de se connecter.

  - **Bloquer et mettre à niveau** Empêche le client de se connecter et permet au client de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update. Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .

  - **Bloquer avec une URL** : empêche le client de se connecter et affiche un message à l’emplacement de téléchargement d’une autre version du client. Vous devez spécifier l’URL dans le champ **URL**.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, voir [interopérabilité client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.

