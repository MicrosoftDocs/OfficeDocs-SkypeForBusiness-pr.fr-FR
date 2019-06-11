---
title: 'Lync Server 2013: configuration de la stratégie globale d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccb5ba267c3dc94e14f00cf96f240fa2f0e91b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configuration de la stratégie globale d’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

Lorsque vous déployez votre serveur frontal, Lync Server crée une stratégie globale d’archivage. Par défaut, l’archivage est désactivé dans la stratégie globale. La stratégie globale contrôle l’activation de l’archivage pour les communications internes et externes pour votre déploiement complet, sauf si vous configurez des stratégies de site ou d’utilisateur qui remplacent la stratégie globale ou si vous utilisez l’intégration de Microsoft Exchange pour tout ou partie de vos utilisateurs. Si vous utilisez l’intégration de Microsoft Exchange, la stratégie global ne s’applique pas aux utilisateurs hébergés sur Exchange 2013 et ayant recours à des boîtes aux lettres pour la conservation inaltérable.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie pour les stratégies globales, de site et d’utilisateur, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, documentation de déploiement, ou documentation sur les opérations.

<div>


> [!NOTE]  
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de conservation sur place permettent de contrôler si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Pour configurer la stratégie globale de l’archivage lors de l’utilisation de bases de données d’archivage Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server 2013, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.

4.  Dans la page **Stratégie d’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie d’archivage - Globale**, procédez comme suit :
    
      - Dans **Nom**, si vous ne souhaitez pas utiliser le nom par défaut Global, spécifiez un nouveau nom pour la stratégie globale.
    
      - Dans **Description**, fournissez des informations sur la stratégie (par exemple, stratégie globale de *nom_division*).
    
      - Afin de contrôler l’archivage des communications internes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Afin de contrôler l’archivage des communications externes pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

