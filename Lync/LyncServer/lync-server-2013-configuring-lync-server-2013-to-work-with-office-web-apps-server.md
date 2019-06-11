---
title: Configuration de Lync Server 2013 pour fonctionner avec Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Configuration de Lync Server 2013 pour fonctionner avec Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-04-22_

Pour pouvoir configurer Lync Server 2013 de manière à utiliser Office Web Apps Server, Office Web Apps Server doit être déployé et configuré. Pour plus d’informations sur l’installation et la configuration d’une batterie de serveurs Office Web Apps Server, voir le Guide de mise en route d’Office Web Apps Server **et d’Office Web** apps pour plus d’informations sur l’installation et la configuration d’une batterie de serveurs Office Web Apps Server. totale.

Après l’installation réussie d’Office Web Apps Server et la configuration correcte de votre batterie de serveurs Web, vous devez configurer Lync Server pour communiquer avec le nouveau serveur. pour ce faire, ajoutez l’URL de découverte d’Office Web Apps Server à votre topologie de serveur Lync. Pour ajouter Office Web Apps Server à votre topologie, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans la boîte de dialogue **Générateur de topologies**, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.

3.  Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier\**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite extraire et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.

4.  Dans le générateur de topologie, développez **Lync Server 2013**, développez le nom de votre site, développez **Pools front end Enterprise Edition**, cliquez avec le bouton droit sur le nom de l’un de vos pools, puis cliquez sur **modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).

6.  Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
    Si Office Web Apps Server est installé en local et dans la même zone réseau que Lync Server 2013, l’option **Office Web Apps Server déployée sur un réseau externe (c’est-à-dire le périmètre/Internet)** ne doit pas être sélectionnée.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.

7.  Dans la boîte de dialogue **définir un nouveau serveur Office Web Apps** , cliquez sur **OK**, puis sur **OK** dans la boîte de dialogue **modifier les propriétés** . L’URL de découverte d’Office Web Apps figure alors sous la forme d’une des associations du pool.

Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.

Après avoir ajouté l’URL de découverte à la topologie, vous devez publier cette topologie mise à jour. Pour cela, dans le Générateur de topologie :

1.  Cliquez sur **Action**, puis sur **Publier la topologie**.

2.  Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.

3.  Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.

4.  Fermez le Générateur de topologie.

</div>

<span> </span>

</div>

</div>

</div>

