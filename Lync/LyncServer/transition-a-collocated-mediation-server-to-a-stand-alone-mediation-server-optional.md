---
title: Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>Transition d’un serveur de médiation colocalisé vers un serveur de médiation autonome (facultatif)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Utilisez la procédure ci-dessous pour migrer votre serveur de médiation, en colocalisé sur votre serveur Standard Edition ou votre liste frontale, vers un serveur de médiation autonome pour un déploiement sur site unique.

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>Pour migrer un serveur de médiation colocalisé vers un serveur de médiation autonome

1.  Ouvrez une topologie existante à partir du générateur de topologie.

2.  Dans le volet gauche, accédez à **pools de médiation**.

3.  Cliquez avec le bouton droit sur pools de **médiation** et sélectionnez **nouveau serveur de médiation**.

4.  Dans la page **définir une nouvelle réserve de médiation** , indiquez le nom de domaine complet du nouveau pool de serveurs de médiation. Déterminez également si ce pool sera un serveur unique ou un pool multiserveur, puis cliquez sur **suivant**.

5.  Sélectionnez le pool de serveurs front end du prochain tronçon vers lequel le nouveau serveur de médiation va diriger les appels entrants, puis cliquez sur **suivant**.

6.  Sélectionnez le pool de bords à utiliser par le serveur de médiation, puis cliquez sur **suivant**.

7.  Sur la page **Specify PSTN passerelles** , associez la passerelle RTC précédente au serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Ajouter**.

8.  Cliquez sur **Terminer** pour fermer l’Assistant **définir un nouveau pool de médiation** .

9.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server 2013**.

10. Dans le volet **actions** , sélectionnez **publier la topologie** et terminer l’Assistant.

11. Suivez les étapes décrites dans l' [article installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur de médiation.

12. Une fois les fichiers installés sur le serveur de médiation, revenez au générateur de topologie et dans le volet gauche, accédez au pool.

13. Cliquez avec le bouton droit sur la liste, puis sélectionnez **modifier les propriétés**.

14. Sous **serveur de médiation**, décochez la case Activer le **serveur de médiation** , puis cliquez sur **OK**.

15. Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server 2013**.

16. Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant.

</div>

</div>

<span> </span>

</div>

</div>

</div>

