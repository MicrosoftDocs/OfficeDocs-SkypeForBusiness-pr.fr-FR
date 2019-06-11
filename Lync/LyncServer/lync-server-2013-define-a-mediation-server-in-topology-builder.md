---
title: 'Lync Server 2013: définir un serveur de médiation dans le générateur de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Définir un serveur de médiation dans le générateur de topologies de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-25_

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir un serveur de médiation autonome ou un pool colocalisé avec un pool frontal sur un site pour lequel vous n’avez pas encore déployé Enterprise Voice.

Vous pouvez définir une topologie à l’aide d’un compte membre du groupe administrateurs.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Définir un serveur de médiation en tant que pool frontal

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir un serveur de médiation colocalisé vers un pool frontal dans un site sur lequel Enterprise Voice n’a pas encore été déployé.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Pour ajouter un serveur de médiation à un pool frontal

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un pool frontal.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de réserve frontale souhaité, puis cliquez sur **nouveau pool frontal..**.

4.  Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.

5.  Dans **sélection de rôles de serveur**colocalisés, activez l’option **Collocate médiation Server**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Si le type de réserve frontale que vous avez sélectionné est l’édition entreprise, le composant serveur de médiation sera installé sur tous les serveurs front-end de cette liste frontale.</P>
    > <LI>
    > <P>Le <STRONG>pool de prochains tronçons</STRONG> utilisé par le serveur de médiation sera le pool frontal sur lequel est colocalisé le serveur de médiation.</P>
    > <LI>
    > <P>Le <STRONG>pool Edge</STRONG> utilisé par le serveur de médiation sera le même pool de périphérie associé au pool frontal sur lequel est localisé le serveur de médiation.</P></LI></UL>

    
    </div>

6.  Cliquez sur **définir par défaut** pour utiliser ce pool frontal pour acheminer les appels à partir de Microsoft Office Communications Server 2007 R2 vers PSTN.

7.  Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.
    
    <div>
    

    > [!NOTE]  
    > Avant de passer à l’étape suivante du processus de déploiement de voix entreprise, assurez-vous que le pool de serveurs de médiation (c’est-à-dire le pool frontal doté du composant de serveur de médiation) utilise les noms de domaine complets que vous avez spécifiés.

    
    </div>

8.  Ensuite, suivez les procédures décrites dans la rubrique [publier la topologie de Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation du Guide de déploiement pour ajouter le serveur de médiation à votre topologie avant de passer à l’étape suivante de la modification des ports d’écoute du serveur de médiation, si nécessaire. Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour définir ou modifier votre topologie.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Définir un serveur de médiation autonome

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir un serveur de médiation autonome ou un pool sur un site sur lequel Enterprise Voice n’a pas encore été déployé.

Si vous avez déjà déployé des serveurs de médiation colocalisés vers ce site, vous pouvez ignorer cette section et [installer les fichiers pour le serveur de médiation dans Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) avant de procéder à la [configuration de Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Cette section suppose que vous avez déjà configuré au moins un pool frontal, comme décrit dans la rubrique <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publier la topologie dans Lync Server 2013</A> dans le Guide de déploiement. accompagnant.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Pour ajouter un serveur de médiation

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un serveur de médiation.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud Pools de **médiation** , puis cliquez sur **pool de serveurs de médiation**.

4.  Dans **définir un nouveau pool de médiation**, tapez le nom de domaine complet (FQDN) du pool de serveurs de médiation.

5.  Effectuez ensuite l’une des opérations suivantes :
    
      - Si vous voulez déployer plusieurs serveurs de médiation dans le pool afin d’offrir une disponibilité élevée, sélectionnez **plusieurs pools d’ordinateurs**.
        
        <div>
        

        > [!NOTE]  
        > Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs de médiation qui disposent de plusieurs serveurs de médiation. Pour plus d’informations, consultez la section utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation de l' <A href="lync-server-2013-dns-load-balancing.md">équilibrage de charge DNS dans Lync Server 2013</A> dans la documentation de planification.

        
        </div>
    
      - Si vous voulez déployer un seul serveur de médiation dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez **pool d’ordinateurs unique**. Ignorez l’étape suivante.

6.  Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , cliquez sur **réserve de sauts suivant**, sur le nom de domaine complet (FQDN) du pool frontal qui utilisera ce pool de serveurs de médiation, puis cliquez sur **suivant**.

8.  Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :
    
      - Si vous voulez fournir une connectivité RTC aux utilisateurs externes activés pour Enterprise Voice, sous **Sélectionner le pool de périphériques utilisés par ce serveur de médiation**, cliquez sur le nom de domaine complet (FQDN) du pool de serveur Edge qui utilisera ce pool de serveurs de médiation pour fournir une connectivité PSTN à utilisateurs externes, puis cliquez sur **suivant**.
    
      - Si vous envisagez de ne pas autoriser les utilisateurs externes pour les voix d’entreprise, ou si vous ne souhaitez pas fournir de connectivité RTC aux utilisateurs en dehors du réseau interne, cliquez sur **suivant**.

9.  Ensuite, suivez les procédures décrites dans [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement pour ajouter le serveur de médiation à la topologie. Vous devez publier votre topologie chaque fois que vous utilisez le générateur de topologie pour créer ou modifier votre topologie de manière à ce que les données puissent être utilisées pour installer les fichiers des serveurs exécutant Lync Server. Passez ensuite aux étapes suivantes pour modifier les ports d’écoute sur le serveur de médiation, si nécessaire.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Définir les ports d’écoute du serveur de médiation

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir les ports d’écoute d’un serveur de médiation ou d’un pool qui acceptera les connexions entrantes d’un homologue de passerelle.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Pour modifier les ports d’écoute du serveur de médiation

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans le générateur de topologie, dans l’arborescence de la console, développez le nœud Pools de **médiation** , puis cliquez avec le bouton droit sur le serveur de médiation précédemment créé.

3.  Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS provenant de Lync Server, 5067 pour le trafic TLS d’homologues (passerelles, PBXes ou SBCs). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.

4.  Spécifiez la plage de port d’écoute TCP ou TLS souhaitée le serveur de médiation acceptera les connexions entrantes des passerelles RTC.
    
    <div>
    

    > [!NOTE]  
    > Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option <STRONG>Activer le port TCP</STRONG> n’est pas activée. Ce paramètre est facultatif.

    
    </div>

Ensuite, [définissez une passerelle dans le générateur de topologie de Lync server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) et installez les fichiers sur chaque serveur de médiation du pool en suivant les procédures décrites dans [installer le fichier pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

