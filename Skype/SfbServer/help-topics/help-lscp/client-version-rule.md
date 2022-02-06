---
title: Règle de version du client
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Une stratégie de version du client est composé d’un ensemble de règles de version des clients. Ces règles définissent les actions à prendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de clients spécifiques.
---

# <a name="client-version-rule"></a>Règle de version du client

Une stratégie de version du client est composé d’un ensemble de règles de version des clients. Ces règles définissent les actions à prendre lorsque les utilisateurs tentent de se connecter avec des clients et des versions de clients spécifiques.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client** :

- Ajoutez de nouvelles règles à une stratégie de version du client.

- Modifier les règles qui font une stratégie de version du client existante

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Agent utilisateur** Vous pouvez sélectionner un type de client dans la liste. Le tableau suivant définit les codes d’agent utilisateur.

|**Nom du client**|**Agent utilisateur**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Téléphone Edition, Office Communicator Téléphone  <br/> |OCPhone  <br/> |
|Communicator Téléphone Edition Platform  <br/> |CPE  <br/> |
|Plateforme de communications unifiées  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client communications en temps réel  <br/> |RTC  <br/> |
|Lync 2010 for iPad  <br/> |iPadLync  <br/> |
|Lync 2010 for iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 for Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 pour Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 pour Android  <br/> |AndroidLync  <br/> |
|Service de mobilité  <br/> |McxService  <br/> |

- **Numéro de version** Vous pouvez spécifier les numéros de version pour les champs suivants ou utiliser des caractères génériques pour indiquer le numéro de version du client.

  - **Version principale** Spécifie le nombre qui correspond à la version majeure du client.

  - **Version mineure** Spécifie le nombre qui correspond à la version mineure du client.

  - **Build** Spécifie le numéro de build qui correspond à la version principale et mineure du client.

  - **Mettre à jour** Spécifie le numéro qui correspond à la version mise à jour du client.

- **Opération de comparaison** Vous pouvez spécifier l’opération de correspondance pour la version du client que vous avez spécifiée dans les étapes précédentes. Les opérations suivantes sont disponibles :

  - **Identique à**

  - **N’est pas**

  - **Plus récent que**

  - **Plus récent ou identique**

  - **Plus ancien que**

  - **Plus ancien ou identique**

- **Action** Vous pouvez spécifier l’action à effectuer lorsque les critères des étapes précédentes sont satisfaits. Les actions suivantes sont disponibles :

  - **Autoriser** Permet au client de se connecter.

  - **Autoriser et mettre à niveau** Permet au client de se connecter et de recevoir des mises à jour de Windows Service de mise à jour du serveur ou Microsoft Update. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.

    > [!NOTE]
    > La sélection de cette action entraîne l’affichage d’une notification la prochaine fois que les utilisateurs se connectent Skype Entreprise. La notification indique qu’une mise à jour est disponible, même si les mises à jour n’ont pas encore été publiées sur Windows Server Update Service ou Microsoft Update. Pour éviter toute confusion, vous avez tout intérêt à choisir cette action après que des mises à jour ont été mises à disposition uniquement.

  - **Autoriser avec l’URL** Permet au client de se connecter et affiche un message sur l’endroit où télécharger une autre version du client. Vous spécifiez l’URL dans le **champ URL** .

  - **Bloquer** Empêche le client de se connecter.

  - **Bloquer et mettre à niveau** Empêche le client de se connecter et permet au client de recevoir des mises à jour de Windows Server Update Service ou Microsoft Update. Cette action est uniquement disponible lorsque l’agent utilisateur **OC** est sélectionné.

  - **Bloquer avec une URL** empêche le client de se connecter et affiche un message sur l’endroit où télécharger une autre version du client. Vous spécifiez l’URL dans le **champ URL** .

Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) dans la documentation des opérations.