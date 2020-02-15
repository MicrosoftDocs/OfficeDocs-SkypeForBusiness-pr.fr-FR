---
title: Configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a5cd13b139cb2544e1d89971a8480d1e1fb296
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-04-22_

Pour pouvoir configurer Lync Server 2013 afin d’utiliser Office Web Apps Server, Office Web Apps Server doit être déployé et configuré. Voir le document **Guide de déploiement d’Office Web Apps Server et d’Office Web Apps** pour obtenir des informations détaillées sur la façon d’installer et de configurer un serveur Office Web Apps unique ou pour obtenir des informations sur la façon d’installer et de configurer une batterie de serveurs Office Web Apps Server en vue d’une haute disponibilité.

Une fois l’installation d’Office Web Apps Server correctement effectuée et la configuration correcte de votre batterie de serveurs Web, vous devez configurer Lync Server pour qu’il communique avec le nouveau serveur ; pour ce faire, vous devez ajouter l’URL de découverte d’Office Web Apps Server à votre topologie Lync Server. Pour ajouter le serveur Office Web Apps Server à votre topologie, procédez comme suit :

1.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologies Lync Server**.

2.  Dans la boîte de dialogue **Générateur de topologie**, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.

3.  Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite récupérer et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.

4.  Dans le générateur de topologies, développez **Lync Server 2013**, développez le nom de votre site, développez **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le nom de l’un de vos pools, puis cliquez sur **modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).

6.  Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
    Si Office Web Apps Server est installé sur site et dans la même zone de réseau que Lync Server 2013, l’option le **serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** ne doit pas être sélectionné.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.

7.  Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, cliquez sur **OK**. Ensuite, cliquez sur **OK** dans la boîte de dialogue **Modifier les propriétés**. L’URL de découverte d’Office Web Apps doit alors figurer parmi les associations du pool.

Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.

Après avoir ajouté l’URL de découverte à la topologie, vous devez ensuite publier cette topologie mise à jour. Pour cela, dans le Générateur de topologie :

1.  Cliquez sur **Action**, puis sur **Publier la topologie**.

2.  Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.

3.  Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.

4.  Fermez le Générateur de topologie.

</div>

<span> </span>

</div>

</div>

</div>

