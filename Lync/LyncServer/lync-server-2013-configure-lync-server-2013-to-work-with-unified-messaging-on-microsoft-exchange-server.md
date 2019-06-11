---
title: 'Lync Server 2013 : Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configuration de Lync Server 2013 pour qu’il fonctionne avec la messagerie unifiée sur Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Dernière modification de la rubrique:** 2013-04-03_

Cette étape nécessite l’utilitaire d’intégration de la messagerie unifiée Exchange (OcsUmUtil. exe). Cet outil se trouve sur le serveur 2013 du serveur Lync dans le. \\Fichiers programme\\fichiers communs\\Microsoft Lync Server 2013\\support.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Exécution de l’utilitaire d’intégration de la messagerie unifiée Exchange

L’utilitaire d’intégration de la messagerie unifiée Exchange doit être exécuté à partir d’un compte d’utilisateur présentant les caractéristiques suivantes:

  - L’appartenance aux groupes RTCUniversalServerAdmins et RtcUniversalUserAdmins (qui inclut l’autorisation de lecture des paramètres de messagerie unifiée Exchange Server);

  - Droits d’utilisateur au sein du domaine pour créer des objets de contact dans le conteneur d’unité d’organisation (UO) spécifié.

Lorsque vous exécutez l’utilitaire d’intégration de MU Exchange, il effectue les tâches suivantes:

  - Permet de créer des objets de contact pour chaque standard automatique et numéro d’accès d’abonné qui doivent être utilisés par les utilisateurs d’Enterprise Voice.

  - Vérifie que le nom de chaque plan de numérotation vocale d’entreprise correspond à son contexte téléphonique de messagerie unifiée (MU) correspondant. Cette correspondance est nécessaire uniquement si le plan de numérotation de messagerie unifiée s’exécute sur une version d’Exchange *antérieure* à Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Avant d’exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange, assurez-vous que vous avez réalisé les opérations suivantes:
> <ul>
> <li><p>Créez un ou plusieurs plans de numérotation de messagerie unifiée Exchange, comme décrit dans la documentation du produit Exchange.</p>
> <p>Pour Microsoft Exchange Server 2010, voir &quot;créer un plan&quot; de numérotation <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>de messagerie unifiée à l’adresse.</p>
> <p>Pour Microsoft Exchange Server 2007 Service Pack 1 (SP1), voir &quot;création d’un plan&quot; de NUMÉROTation d’URI SIP de <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>messagerie unifiée à l’adresse.</p></li>
> <li><p>Créez un ou plusieurs plans de numérotation Lync Server correspondants, comme décrit dans la rubrique <a href="lync-server-2013-create-a-dial-plan.md">créer un plan de numérotation dans Lync Server 2013</a>.</p></li>
> <ul><li>Si vous utilisez une version d’Exchange antérieure à Microsoft Exchange Server 2010 SP1, vous devez entrer le nom de domaine complet (FQDN) du plan de numérotation SIP correspondant dans le plan de numérotation de messagerie unifiée Exchange Server 2013. <STRONG> </STRONG>champ. Si vous utilisez Microsoft Exchange Server 2010 SP1 ou le dernier Service Pack, il n’est pas nécessaire de faire correspondre ce nom de plan de numérotation.</li></ul>
> <li>Créez un standard automatique et assurez-vous que le numéro d’accès d’abonné et le numéro de standard automatique sont au format E. 164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Pour exécuter l’utilitaire d’intégration de la messagerie unifiée Exchange

1.  Sur un serveur frontal, ouvrez une invite de commandes et tapez **cd% COMMONPROGRAMFILES%\\Microsoft Lync Server 2013\\support**, puis appuyez sur entrée.

2.  Tapez **OcsUmUtil. exe**, puis appuyez sur entrée.

3.  Cliquez sur **charger les données** pour rechercher toutes les forêts Exchange approuvées.

4.  Dans la liste **plans de numérotation SIP** , sélectionnez un plan de numérotation SIP de MU pour lequel vous voulez créer des objets de contact, puis cliquez sur **Ajouter**.

5.  Dans la zone **contact** , acceptez l’unité d’organisation par défaut ou cliquez sur **Parcourir** pour démarrer le **Sélecteur d’UO**. Dans la boîte de dialogue **Sélecteur d’UO** , vous pouvez sélectionner une unité d’organisation et cliquer sur **OK**, ou bien cliquer sur **créer une nouvelle** unité d’organisation pour créer une nouvelle unité d’organisation sous la racine OU dans une autre unité d’organisation du domaine (par exemple, «UO = RTC spécial, DC = fourthcoffee, DC = com») , puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Le nom unique (DN) de l’unité d’organisation que vous avez sélectionnée ou créée est désormais affiché dans la zone <STRONG>unité d’organisation</STRONG> .

    
    </div>

6.  Dans la zone **nom** , acceptez le nom de plan de numérotation par défaut ou tapez un nouveau nom d’affichage pour l’objet de contact que vous êtes en train de créer.
    
    <div>
    

    > [!NOTE]  
    > Par exemple, si vous créez un objet contact d’accès abonné, vous pouvez simplement lui nommer l’accès de l’abonné.

    
    </div>

7.  Dans la zone **adresse SIP** , acceptez l’adresse SIP par défaut ou tapez une nouvelle adresse SIP.
    
    <div>
    

    > [!NOTE]  
    > Si vous tapez une nouvelle adresse SIP, celle-ci doit commencer par <STRONG>SIP:</STRONG> (c’est-À-dire «SIP:», y compris le signe deux-points).

    
    </div>

8.  Dans la liste **serveur ou pool** , sélectionnez le serveur Standard Edition ou le pool frontal sur lequel l’objet de contact doit être activé.
    
    <div>
    

    > [!NOTE]  
    > De préférence, le pool que vous sélectionnez est le même que celui dans lequel les utilisateurs sont activés pour voix entreprise et Exchange UM.

    
    </div>

9.  Dans la liste **numéro de téléphone** , sélectionnez **saisir le numéro de téléphone** ou **utiliser ce pilote à partir d’Exchange um** , puis entrez un numéro de téléphone.

10. Dans la liste **type de contact** , sélectionnez le type de contact que vous voulez créer, puis cliquez sur **OK**.

11. Répétez les étapes 1 à 10 pour les autres objets de contact que vous voulez créer.
    
    <div>
    

    > [!NOTE]  
    > Vous devez créer au moins un contact pour chaque standard automatique. Si vous voulez disposer d’un accès externe, vous devez également disposer d’un contact d’accès d’abonné et spécifier des numéros directs de composition à l’intérieur.

    
    </div>

</div>

Pour vérifier que les objets de contact ont été créés, ouvrez utilisateurs et ordinateurs Active Directory, puis sélectionnez l’unité d’organisation dans laquelle les objets ont été créés. Les objets de contact doivent s’afficher dans le volet Détails.

</div>

</div>

<span> </span>

</div>

</div>

</div>

