---
title: Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

L’outil de filtrage de messages instantanés intelligents vous aide à protéger votre déploiement de Lync Server 2013 contre la répartition des formes les plus fréquemment utilisées avec une dégradation minimale de l’interface utilisateur. Utilisez le filtre de message instantané intelligent pour configurer des filtres permettant de bloquer les messages instantanés non sollicités ou potentiellement dangereux de points de terminaison inconnus en dehors du pare-feu de l’entreprise. Vous pouvez configurer des filtres en spécifiant les critères à utiliser pour déterminer ce qui devrait être bloqué (par exemple, les messages instantanés contenant des liens hypertexte avec des préfixes spécifiques et des fichiers avec des extensions spécifiques).

Le filtre de message instantané intelligent fournit les éléments suivants:

  - Amélioration du filtrage d’URL.

  - Amélioration du filtrage du transfert de fichiers.

La configuration du filtre de message instantané intelligent inclut les éléments suivants:

  - Configuration du filtrage d’URL.

  - Configuration du filtrage de transfert de fichiers.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Application des options de filtre aux messages instantanés

Avant de déployer l’outil de filtre de messages INSTANTANÉs intelligents, vous devez comprendre comment les options de filtre sont appliquées lorsque les messages sont routés d’un serveur Lync Server 2013 vers un autre. La façon dont ces options de filtrage sont appliquées est cohérente, qu’il s’agisse de serveurs au sein d’une organisation unique ou de limites de l’organisation. Cette cohérence s’applique au mode d’insertion des avis personnalisés et des textes d’avertissement dans les messages et envoyés sur plusieurs serveurs.

<div>


> [!NOTE]
> Le filtre de message instantané augmente le volume de ressources processeur requises pour traiter les URL d’un message. Cette augmentation de la demande de l’UC affecte également les performances de Lync Server.



</div>

À l’aide de la page de **filtre d’URL** du groupe **messagerie instantanée et présence** dans le panneau de configuration de Lync Server, vous pouvez bloquer tout ou partie des liens hypertexte ou configurer un avertissement. Le message d’avertissement est inséré au début d’un message instantané contenant un lien hypertexte lorsque vous sélectionnez l’option **lien hypertexte** : préfixe de l’option **Envoyer un message d’avertissement**.

Lorsqu’un message instantané est acheminé d’un serveur à un autre, les instructions générales suivantes s’appliquent:

  - Si un serveur bloque un message instantané (puisque vous avez activé la case à cocher **bloquer les URL avec l’extension de fichier** dans la page filtre d' **URL** ou que vous avez choisi l’option **lien hypertexte** : **bloquer les liens**hypertexte), un message d’erreur est renvoyé à le client. Les serveurs suivants ne reçoivent pas ce message instantané.

  - Si un serveur (serveur1) ajoute un avertissement à un message instantané contenant un lien hypertexte actif, un serveur ultérieur (server2) qui reçoit ce message instantané peut toujours effectuer une autre action en fonction de cet hyperlien actif présent dans le message instantané et bloquer le Envoyer un message instantané ou ajouter un avertissement. Si Server2 est configuré uniquement pour ajouter un avertissement pour cette URL, l’avertissement précédent ajouté par Server1 est supprimé et l’avertissement configuré sur Server2 est ajouté au début du message instantané.

<div>


> [!NOTE]
> Si vous exécutez Lync Server 2013 dans un environnement mixte, Live Communications Server 2005 avec SP1 est la version minimale requise pour utiliser l’application de filtre de message instantané intelligent. Le filtre de messagerie instantanée intelligent n’est pas pris en charge sur Live Communications Server 2005 sans SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtrage d’URL

Les URL sont filtrées en fonction de leur préfixe de lien hypertexte. Les exemples suivants sont des préfixes valides:

  - www\*.

  - FTP.

  - http

Si vous ne configurez pas le filtre des messages instantanés pour effectuer un filtrage d’URL, toutes les URL contenues dans les messages instantanés ne sont pas modifiées par le biais du serveur. Si vous configurez le filtre des messages instantanés pour effectuer le filtrage d’URL, les URL dans les messages instantanés sont filtrées conformément aux options que vous avez sélectionnées dans la boîte de dialogue **modifier le filtre d’URL** ou **nouveau filtre d’URL** .

  - **Activer le filtre**   d’URL cette option active le filtrage d’URL pour le déploiement global ou pour le site que vous sélectionnez.

  - **Bloquer les URL avec l’extension**   de fichier le filtre de message instantané bloque toutes les URL Internet ou intranet actives qui contiennent un fichier doté d’une extension répertoriées sous **extensions de type de fichier à bloquer** dans la boîte de dialogue **modifier le filtre de fichiers** . Lorsqu’une URL est bloquée, un message d’erreur s’affiche à l’expéditeur. Lorsque cette option est sélectionnée, elle est prioritaire sur toutes les autres options de filtrage pour les extensions de fichiers définies sous **extensions de type de fichier à bloquer**.
    
    <div>
    

    > [!IMPORTANT]
    > Le filtrage d’extensions de fichier est limité aux noms de fichiers standard. Il est possible que le filtrage ne fonctionne pas avec les extensions de fichier imbriquées dans d’autres noms.

    
    </div>

Pour configurer la gestion des liens hypertexte dans les conversations par messagerie instantanée, sélectionnez l’une des options suivantes sous préfixe du **lien hypertexte**:

  - **Ne filtrez**   pas les URL des messages envoyés par le biais du serveur. Lorsque vous choisissez cette option, la boîte de **dialogue autoriser le message** s’affiche. Dans la boîte de dialogue **autoriser le message** , spécifiez l’avis que vous voulez insérer au début de chaque message instantané contenant des liens hypertexte. Ce message ne peut pas contenir plus de 65535 caractères.

  - **Bloquer**   la remise de liens hypertexte pour les messages instantanés contenant des liens hypertexte actifs est bloqué par Lync Server et un message d’erreur s’affiche à l’expéditeur.

  - **Envoyer un message**   d’avertissement Lync Server autorise les liens hypertexte actifs dans les messages instantanés, mais il inclut un avertissement. Lorsque vous choisissez cette option, la boîte de **dialogue Avertissement** s’affiche. Dans la boîte de **dialogue message d’avertissement** , vous devez taper l’avertissement que vous voulez inclure dans les messages instantanés contenant des liens hypertexte valides. Par exemple, ce message d’avertissement peut faire référence aux dangers potentiels d’un clic sur un lien inconnu, ou faire référence aux politiques et exigences pertinentes de votre organisation. Le message d’avertissement ne peut pas contenir plus de 65535 caractères.

Si vous sélectionnez **bloquer les liens hypertexte** ou **Envoyer un message d’avertissement**, les options suivantes sont disponibles:

  - **Exclure les liens hypertexte de l’intranet local**   le filtre de message instantané bloque uniquement les URL Internet. Les URL des emplacements au sein de votre intranet sont transmises sans modification sur le serveur. Toutefois, les URL de l’intranet qui sont prises en charge par les serveurs exécutant Lync Server en fonction des types de sites Web locaux qui sont considérés comme faisant partie de leur zone intranet. Pour vérifier les paramètres de zone intranet d’un serveur, reportez-vous à la procédure «pour configurer vos paramètres intranet dans Internet Explorer» dans [modifier le filtre d’URL par défaut dans Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrer ces**   préfixes pour sélectionner les préfixes que vous voulez bloquer, cliquez sur **Sélectionner**, puis, dans **Sélectionner un préfixe de lien hypertexte**, ajoutez les préfixes à la liste préfixes du **lien hypertexte** .
    
    Tous les préfixes sauf **href** doivent se terminer par un point ou une virgule, ou un astérisque suivi par un point. Les préfixes valides peuvent contenir des caractères dans l’ensemble de caractères d’URL valides sauf l’astérisque (\*). Le jeu de caractères d’URL valides \# \*est: +/0123456789 =\_ \` @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtrage du transfert de fichiers

Le filtrage de transfert de filtre affecte les messages instantanés et les conférences. En ce qui concerne les conférences, ces paramètres affectent la fonctionnalité documents du client Office Live Meeting 2007 et des fonctionnalités de lecture multimédia.

<div>


> [!NOTE]
> Lync Server propose également des options de paramètres de transfert de fichiers. Cette option côté serveur est proposée en plus des contrôles côté client disponibles dans Lync Server.



</div>

Vous pouvez filtrer les transferts de fichiers lors des conversations par messagerie instantanée, lorsque vous utilisez la fonctionnalité documents du client 2007 Office Live Meeting et des fonctionnalités de lecture multimédias pour tous les types de fichiers. Vous pouvez définir les options suivantes pour contrôler les transferts de fichiers:

  - **Activer le filtre**   de fichiers cette option active le filtrage de fichiers pour le déploiement global ou pour le site que vous sélectionnez.
    
    Lorsque vous activez le filtre de fichier, vous pouvez choisir l’une des options suivantes dans **transfert de fichier**:
    
      - **Bloquer des types**   de fichiers spécifiques vous spécifiez les demandes de transfert de fichiers filtrées par le serveur en spécifiant une liste d’extensions de fichier à bloquer. Les entrées de la liste peuvent contenir tous les caractères standard, à l’exception du\*caractère générique (). Dans le client Office Live Meeting 2007, la fonctionnalité documents est activée alors qu’il n’est pas possible de télécharger ou de télécharger un fichier avec cette extension. Si vous activez la case à cocher **bloquer les URL avec l’extension de fichier** dans les paramètres d’un filtre d’URL indiqué dans l’onglet filtre d' **URL** , le filtre d’URL utilise la même liste pour bloquer les liens hypertexte actifs qui contiennent l’une de ces extensions de fichier. Pour choisir les types de fichiers que vous souhaitez bloquer, cliquez sur **Sélectionner**, puis, sous **type de fichier**, ajoutez les extensions de type de fichier à la liste extensions de type de fichier **sélectionnées** .
    
      - **Bloquer tout**   le serveur supprime tous les messages instantanés qui contiennent des demandes de transfert de fichiers et renvoie un message d’erreur à l’expéditeur de la requête. La fonctionnalité documents du client 2007 Office Live Meeting est désactivée.

<div>


> [!IMPORTANT]
> Le filtrage d’extensions de fichier est limité aux noms de fichiers standard. Il est possible que le filtrage ne fonctionne pas avec les extensions de fichier imbriquées dans d’autres noms.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des paramètres de messagerie instantanée et de présence dans Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

