---
title: 'Lync Server 2013: modification du diagramme de configuration réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Modification du diagramme de configuration réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

La majeure partie du travail qu’un concepteur effectue dans l’outil de planification de Lync Server 2013 (en anglais) consiste à définir les entrées pour les adresses IP et les noms de domaine complets (FQDN) pour les entrées sur le réseau de tâches. Les informations entrées dans cette page sont incluses dans les rapports et autres informations contenus dans l’outil de planification.

![Diagramme du réseau d’outils de planification] (images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagramme du réseau d’outils de planification")

L’outil de planification crée un diagramme de réseau avec le texte par défaut pour les adresses IP et les noms de domaine complets.

Pour modifier le diagramme de réseau et les valeurs entrées :

1.  Commencez par choisir une section du réseau. Par exemple, double-cliquez sur le texte **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet (FQDN) réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant 131.107.155.3.

2.  Cliquez sur **OK** pour enregistrer les entrées.

3.  Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.

Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :

1.  Double-cliquez sur les serveurs frontaux du pool. Quand la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.

2.  Dans l’exemple, la valeur de démarrage pour le premier serveur est fe0101.contoso.com avec l’adresse IP 192.168.21.122.

3.  Tapez **fe0.contoso.com** dans le **nom de domaine complet du serveur frontal**, tapez **192.168.21.131** dans l’**Adresse IP du serveur frontal**, puis cliquez sur **OK**.

4.  La fonction d’incrémentation automatique met à jour tous les serveurs du pool entre fe01 et fe06, et toutes les adresses IP entre 192.168.21.131 et 136.

Une fois toutes les modifications terminées, enregistrez la topologie en procédant comme suit :

Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis sur **enregistrer la topologie** ou **enregistrer la topologie sous**. Si une boîte de dialogue **Enregistrer l’outil de planification sous** s’affiche, tapez un nom pour le fichier dans **Nom de fichier**, puis cliquez sur **Enregistrer**.

<div>

## <a name="see-also"></a>Voir aussi


[Modification de la conception dans Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

