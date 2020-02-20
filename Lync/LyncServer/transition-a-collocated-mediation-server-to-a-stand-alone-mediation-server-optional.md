---
title: Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e182bc32ba07ae22b2c14cc0a51f36ac93ba57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Transition d’un serveur de médiation colocalisé à un serveur de médiation autonome (facultatif)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Appliquez la procédure qui suit pour effectuer la transition de votre serveur de médiation, colocalisé sur votre serveur Standard Edition ou pool frontal, vers un serveur de médiation autonome pour un déploiement sur un seul site.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Pour passer d’un serveur de médiation colocalisé à un serveur de médiation autonome

1.  Ouvrez une topologie existante à partir du Générateur de topologie.

2.  Dans le volet gauche, naviguez jusqu’à **Pools de médiation**.

3.  Cliquez avec le bouton droit sur **Pools de médiation**, puis cliquez sur **Nouveau serveur de médiation**.

4.  Dans la page **Définir un nouveau pool de médiation**, spécifiez le nom de domaine complet du nouveau pool de serveurs de médiation. Indiquez également s’il s’agit d’un pool de serveur unique ou de plusieurs serveurs, puis cliquez sur **Suivant**.

5.  Sélectionnez le pool de serveurs frontaux du tronçon suivant vers lequel le nouveau serveur de médiation acheminera les appels entrants, puis cliquez sur **Suivant**.

6.  Sélectionnez le pool Edge que doit utiliser le serveur de médiation, puis cliquez sur **Suivant**.

7.  Dans la page **Spécifier des passerelles PSTN**, associez la passerelle PSTN précédente au serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Ajouter**.

8.  Cliquez sur **Terminer** pour fermer l’Assistant **Définir un nouveau pool de médiation**.

9.  Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server 2013**.

10. Dans le volet **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.

11. Suivez les étapes décrites dans [install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur de médiation.

12. Une fois les fichiers installés sur le serveur de médiation, revenez dans le Générateur de topologie et, dans le volet gauche, accédez au pool.

13. Cliquez avec le bouton droit sur le pool et sélectionnez **Modifier les propriétés**.

14. Sous **Serveur de médiation**, décochez la case **Activation de la fonctionnalité de cohabitation du serveur de médiation**, puis cliquez sur **OK**.

15. Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server 2013**.

16. Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.

</div>

</div>

<span> </span>

</div>

</div>

</div>

