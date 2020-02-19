---
title: Empêcher les nouvelles connexions à Lync Server pour la maintenance du serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06516c3d47a9ec5e491a5a16098dfae334ff4f4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Empêcher les nouvelles connexions à Lync Server 2013 pour la maintenance du serveur

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lync Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à niveau logicielles ou matérielles) sans perte de service pour les utilisateurs.

Quand vous spécifiez l’option qui empêche toute nouvelle connexion ou tout nouvel appel sur un serveur appartenant à un pool, Lync Server n’accepte plus de nouvelles connexions, ni de nouveaux appels une fois cette option implémentée. Quand un serveur empêche toute nouvelle connexion, il autorise ses sessions sur des connexions existantes à se poursuivre, jusqu’à ce qu’elles se terminent normalement. Une fois toutes les sessions existantes parvenues à terme, le serveur est prêt à être mis hors connexion.

Lorsque vous interdisez de nouvelles connexions à un serveur frontal, certains services et fonctionnalités Lync Server s’appuient sur l’équilibrage de charge DNS pour s’assurer qu’il fonctionne correctement. Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, les connexions par le biais de ces services ne peuvent pas être redirigées vers d’autres serveurs pendant la période pendant laquelle le serveur empêche les nouvelles connexions et, par conséquent, lorsque le serveur est mis hors connexion, certaines sessions et appels peuvent être fonctionner. Les fonctionnalités qui dépendent de l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :

  - Attendant

  - application d’annonce de conférence

  - Application Response Group

  - application d’annonce

  - application de parcage d’appel

Pour plus d’informations sur l’équilibrage de la charge DNS, voir [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

En plus d’empêcher les nouvelles connexions pour tous les services sur un serveur exécutant Lync Server, vous pouvez également empêcher les nouvelles connexions pour des services Lync Server individuels. Par exemple, cette méthode est utile lorsque vous devez appliquer une mise à jour Lync Server qui ne nécessite pas l’arrêt de l’ensemble du serveur. Veuillez noter que lorsque vous interdisez les connexions pour un service, vous devez sélectionner un service groupé et affiché dans la liste des services Windows. Par exemple, le service frontal Lync Server et l’agent de collecte de données pour la surveillance sont des services Lync Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés en tant que service frontal Lync Server. Vous pouvez empêcher les nouvelles connexions pour le service frontal Lync Server, mais vous ne pouvez pas empêcher les nouvelles connexions pour ces deux services Lync Server sous-jacents individuels.

<div>


> [!IMPORTANT]
> Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Pour empêcher les nouvelles connexions à Lync Server, procédez comme suit :

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Ouvrez la console de composant logiciel enfichable Services : cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **services**.

3.  Dans la liste, double-cliquez sur le service Windows Lync Server auquel vous voulez empêcher les nouvelles connexions.

4.  Dans la boîte de dialogue Propriétés, sous **État du service : Démarré**, cliquez sur **Suspendre**.

5.  La méthode facultative et recommandée consiste à cliquer sur **Manuel**, en regard de **Type de démarrage**.
    
    <div>
    

    > [!IMPORTANT]
    > Quand vous configurez un serveur de manière à empêcher de nouvelles connexions puis que vous le redémarrez, par défaut, le serveur accepte immédiatement les nouvelles connexions après son redémarrage. Pour éviter cela, configurez le serveur de manière à ce qu’il s’interrompe et reprenne uniquement manuellement, puis redémarrez-le.

    
    </div>

6.  Lorsque vous avez terminé, cliquez sur **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

