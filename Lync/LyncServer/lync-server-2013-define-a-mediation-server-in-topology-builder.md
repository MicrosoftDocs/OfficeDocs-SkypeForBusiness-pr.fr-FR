---
title: 'Lync Server 2013 : définition d’un serveur de médiation dans le générateur de topologies'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 782491b0df1c8d2432a9b4c69240293ccc126e7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Définition d’un serveur de médiation dans le générateur de topologies dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-25_

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie afin de définir un serveur de médiation autonome ou un pool colocalisé avec un pool frontal sur un site pour lequel vous n’avez pas déjà déployé voix entreprise.

Vous pouvez définir une topologie à l’aide d’un compte qui est membre du groupe Administrateurs.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Définir un serveur de médiation colocalisé avec un pool frontal

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie afin de définir un serveur de médiation colocalisé avec un pool frontal dans un site où Enterprise Voice n’a pas encore été déployé.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Pour ajouter un serveur de médiation à un pool frontal

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans le générateur de topologies, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool frontal.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de pool frontal souhaité, puis cliquez sur **nouveau pool frontal..**.

4.  Naviguez au sein de l’Assistant permettant de **Définir un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.

5.  Dans **Sélectionner les rôles serveur colocalisés**, activez l’option **colocaliser le serveur de médiation**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Si le type de pool frontal que vous avez sélectionné est Enterprise Edition, le composant de serveur de médiation est installé sur tous les serveurs frontaux de ce pool frontal.</P>
    > <LI>
    > <P>Le <STRONG>pool de tronçon suivant</STRONG> utilisé par le serveur de médiation sera le pool frontal sur lequel le serveur de médiation est colocalisé.</P>
    > <LI>
    > <P>Le <STRONG>pool</STRONG> de serveurs Edge utilisé par le serveur de médiation sera le même pool de serveurs Edge associé au pool frontal sur lequel le serveur de médiation est colocalisé.</P></LI></UL>

    
    </div>

6.  Cliquez sur utiliser **par défaut** pour utiliser ce pool frontal afin d’acheminer les appels de Microsoft Office Communications Server 2007 R2 vers le réseau téléphonique commuté (RTC).

7.  Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.
    
    <div>
    

    > [!NOTE]  
    > Avant de passer à l’étape suivante du processus de déploiement de voix entreprise, assurez-vous que le pool de serveurs de médiation (c’est-à-dire un pool frontal avec le composant de serveur de médiation colocalisé) utilise les noms de domaine complets que vous avez spécifiés.

    
    </div>

8.  Ensuite, suivez les procédures décrites dans [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation du Guide de déploiement pour ajouter le serveur de médiation à votre topologie avant de passer à l’étape suivante de la modification des ports d’écoute du serveur de médiation, si nécessaire. Vous devez publier votre topologie à chaque fois que vous utilisez le générateur de topologies pour définir ou modifier votre topologie.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Définir un serveur de médiation autonome

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie afin de définir un pool ou un serveur de médiation autonome sur un site où Enterprise Voice n’a pas été précédemment déployé.

Si vous avez déjà déployé des serveurs de médiation colocalisés sur des pools frontaux sur ce site, vous pouvez ignorer cette section et [installer les fichiers pour le serveur de médiation dans Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) avant de procéder à la [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Cette section suppose que vous ayez déjà configuré au moins un pool frontal, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> et <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> dans la documentation du Guide de déploiement.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Pour ajouter un serveur de médiation

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans le générateur de topologies, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud **pools de médiation** , puis cliquez sur **pool de serveurs de médiation**.

4.  Dans **définir un nouveau pool de médiation**, tapez le nom de domaine complet (FQDN) du pool de serveurs de médiation.

5.  Effectuez ensuite l’une des opérations suivantes :
    
      - Si vous souhaitez déployer plusieurs serveurs de médiation dans le pool afin de fournir une haute disponibilité, sélectionnez **pool de plusieurs ordinateurs**.
        
        <div>
        

        > [!NOTE]  
        > Vous devez déployer l’équilibrage de la charge DNS pour prendre en charge les pools de serveurs de médiation ayant plusieurs serveurs de médiation. Pour plus d’informations, reportez-vous à la section utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation de l' <A href="lync-server-2013-dns-load-balancing.md">équilibrage de charge DNS dans Lync Server 2013</A> dans la documentation de planification.

        
        </div>
    
      - Si vous ne souhaitez déployer qu’un seul serveur de médiation dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez pool d’un **seul ordinateur**. Ignorez l’étape suivante.

6.  Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.

7.  Dans la page **Sélectionner le tronçon suivant** , cliquez sur **pool du tronçon suivant**, cliquez sur le nom de domaine complet du pool frontal qui utilisera ce pool de serveurs de médiation, puis cliquez sur **suivant**.

8.  Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :
    
      - Si vous souhaitez fournir la connectivité PSTN aux utilisateurs externes activés pour voix entreprise, sous sélectionnez le pool de serveurs Edge **utilisé par ce serveur de médiation**, cliquez sur le nom de domaine complet (FQDN) du pool de serveurs Edge qui utilisera ce pool de serveurs de médiation pour fournir la connectivité PSTN aux utilisateurs externes, puis cliquez sur **suivant**.
    
      - Si vous ne prévoyez pas d’activer les utilisateurs externes pour voix entreprise ou si vous ne souhaitez pas fournir de connectivité PSTN aux utilisateurs lorsqu’ils se trouvent à l’extérieur du réseau interne, cliquez sur **suivant**.

9.  Suivez ensuite les procédures de la [publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement pour ajouter le serveur de médiation à la topologie. Vous devez publier votre topologie à chaque fois que vous utilisez le générateur de topologie pour créer ou modifier votre topologie afin que les données puissent être utilisées pour installer les fichiers pour les serveurs qui exécutent Lync Server. Effectuez ensuite les étapes suivantes afin de modifier si nécessaire les ports d’écoute du serveur de médiation.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Définir les ports d’écoute du serveur de médiation

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie afin de définir les ports d’écoute un serveur de médiation ou un pool acceptera les connexions entrantes à partir d’un homologue de passerelle.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Pour modifier les ports d’écoute du serveur de médiation

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans le générateur de topologies, dans l’arborescence de la console, développez le nœud **pools de médiation** , puis cliquez avec le bouton droit sur le serveur de médiation précédemment créé.

3.  Par défaut, les ports d’écoute SIP du serveur de médiation sont 5070 pour le trafic TLS provenant de Lync Server, 5067 pour le trafic TLS provenant de pairs (passerelles, PBX ou SBC). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.

4.  Spécifier la plage de ports d’écoute TLS ou TCP souhaitée le serveur de médiation accepte les connexions entrantes à partir de passerelles RTC.
    
    <div>
    

    > [!NOTE]  
    > L’entrée d’une plage de ports TCP n’est pas nécessaire, si l’option <STRONG>Activer le port TCP</STRONG> n’est pas activée. Ce paramètre est facultatif.

    
    </div>

Ensuite, [définissez une passerelle dans le générateur de topologies dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) et installez les fichiers sur chaque serveur de médiation du pool en suivant les procédures décrites dans [install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

