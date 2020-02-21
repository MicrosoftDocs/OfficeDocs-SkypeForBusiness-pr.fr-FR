---
title: 'Lync Server 2013 : modification du diagramme de configuration réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225702f30aa19bf53c8b3f65c9731ea29b16a686
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Modification du diagramme de configuration réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

La plupart du travail qu’un concepteur effectue dans l’outil de planification Lync Server 2013, consiste à définir les entrées des adresses IP et des noms de domaine complets (FQDN) pour les entrées sur le réseau de tâches. Les informations qui sont entrées sur cette page sont reportées dans les rapports et les autres informations contenues dans l’outil de planification.

![Diagramme de réseau de l’outil de planification](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagramme de réseau de l’outil de planification")

L’outil de planification crée un diagramme de réseau avec le texte par défaut pour les adresses IP et les noms de domaine complets.

Pour modifier le diagramme de réseau et les valeurs entrées :

1.  Choisissez la section du réseau sur laquelle vous souhaitez commencer à travailler. Par exemple, double-cliquez sur le texte, **access1.contoso.com**. Dans la boîte de dialogue qui s’ouvre, tapez le nom de domaine complet réel du serveur access1.contoso.com et l’adresse IP réelle, en remplaçant le 131.107.155.3.

2.  Cliquez sur **OK** pour enregistrer les entrées.

3.  Continuez à modifier les adresses IP et les noms de domaine complets (FQDN) en spécifiant des adresses IP virtuelles pour les programmes d’équilibrage de la charge matérielle ou des entrées de serveur pour l’équilibrage de la charge DNS des serveurs contenus dans les pools.

Une fonction utile de l’outil de planification est la possibilité d’affecter une plage d’adresses IP et de noms d’hôte de serveur, au lieu de demander au concepteur de modifier chaque serveur d’un pool. Par exemple :

1.  Double-cliquez sur les serveurs frontaux du pool. Lorsque la boîte de dialogue s’ouvre, sélectionnez **Souhaitez-vous utiliser les adresses IP et les noms de domaine complets (FQDN) comme points de départ pour tous les serveurs équivalents dans ce cluster ?**.

2.  Par exemple, la valeur de départ du premier serveur est fe0101.contoso.com et l’adresse IP 192.168.21.122.

3.  Tapez **Fe0.contoso.com** dans **nom de domaine complet du serveur frontal**, tapez **192.168.21.131** dans **adresse IP du serveur frontal**, puis cliquez sur **OK**.

4.  La fonctionnalité d’auto-incrémentation met à jour tous les serveurs du pool vers entre FE01 via fe06 et toutes les adresses IP de 192.168.21.131 à 136.

Une fois que vous avez terminé toutes les modifications, enregistrez la topologie en procédant comme suit :

Pour enregistrer la conception de l’outil de planification, cliquez sur **fichier**, puis sur **Enregistrer** la topologie ou sur **enregistrer la topologie sous**. Si une boîte de dialogue **Enregistrer l’outil de planification sous le nom** s’affiche, tapez un nom pour le fichier dans **Nom du fichier**, puis cliquez sur **Enregistrer**.

<div>

## <a name="see-also"></a>Voir aussi


[Modification de la conception dans Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

