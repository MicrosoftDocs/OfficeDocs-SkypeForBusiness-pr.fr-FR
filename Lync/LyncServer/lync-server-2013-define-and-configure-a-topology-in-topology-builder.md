---
title: 'Lync Server 2013 : Définition et configuration d’une topologie dans le générateur de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

L’exécution du générateur de topologie pour définir une nouvelle topologie ou la modification d’une topologie existante ne nécessite pas d’appartenance à un administrateur local ou à un groupe de domaine privilégié. Le générateur de topologie vous guide au cours des étapes nécessaires à la définition de votre topologie pour une liste frontale Enterprise Edition ou une édition standard, en fonction de vos besoins en matière de configuration.

Vous devez utiliser le générateur de topologie pour achever et publier la topologie avant de pouvoir installer Lync Server 2013 sur des serveurs. La procédure suivante présente les étapes nécessaires pour définir une nouvelle topologie.

<div>

## <a name="to-define-a-topology"></a>Pour définir une topologie

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans le générateur de topologie, sélectionnez **nouvelle topologie**. Vous êtes invité à entrer un emplacement et un nom de fichier pour l’enregistrement de la topologie. Donnez un nom significatif au fichier de topologie et acceptez l’extension par défaut de. tbxml. Cliquez sur **OK**.

3.  Accédez à l’emplacement où vous voulez enregistrer le nouveau fichier XML de topologie, entrez un nom pour le fichier, puis cliquez sur **Enregistrer**.

4.  Dans la page **définir le domaine principal** , entrez le nom du domaine SIP principal de votre organisation, puis cliquez sur **suivant**.

5.  Dans la page **spécifier d’autres domaines pris en charge** , entrez le nom des domaines supplémentaires, le cas échéant, puis cliquez sur **suivant**.

6.  Dans la page **définir le premier site** , entrez un nom et une description pour le premier site, puis cliquez sur **suivant**.

7.  Dans la page **spécifier les détails du site** , entrez les informations d’emplacement du site, puis cliquez sur **suivant**.

8.  Dans la page **nouvelle topologie définie avec succès** , assurez-vous que la case à cocher **ouvrir l’Assistant Nouveau serveur frontal à la fermeture de cet Assistant** est activée, puis cliquez sur **Terminer**.

Une fois que vous avez défini et enregistré la topologie, utilisez le nouvel Assistant frontal pour définir un pool frontal ou un serveur Standard Edition Server pour votre site. Pour plus d’informations, reportez-vous à [la section définir et configurer un pool frontal ou un serveur Standard Edition Server dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

