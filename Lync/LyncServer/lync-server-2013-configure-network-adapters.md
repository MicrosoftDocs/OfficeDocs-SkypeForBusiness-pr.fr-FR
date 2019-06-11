---
title: 'Lync Server 2013 : Configuration des cartes réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3469e9d5fa3f7aeb45bc8f35ff692d97d09b8481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Configuration des cartes réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Vous devez assigner une ou plusieurs adresses IP à la carte réseau externe et au moins une adresse IP à la carte réseau interne.

Dans les procédures suivantes, le serveur qui exécute le routage de demandes d’applications de la passerelle de gestion des menaces (TMG) 2010 ou de l’application Internet Information Server est doté de deux cartes réseau:

  - Une carte réseau publique ou externe, qui permet aux clients qui essaient de se connecter à votre site Web (généralement sur Internet).

  - Une interface réseau privée, ou interne, pour les serveurs internes exécutant Lync Server hébergeant des services Web.

<div>


> [!IMPORTANT]  
> Comme pour les serveurs Edge, vous définissez la passerelle par défaut sur la carte réseau externe uniquement. La passerelle par défaut est l’adresse IP du routeur ou du pare-feu externe qui dirige le trafic vers Internet. Pour le trafic qui provient du proxy inverse vers la carte réseau interne, vous devez utiliser des itinéraires statiques persistants (tels que la commande itinéraire dans Windows Server) pour tous les sous-réseaux contenant des serveurs référencés par les règles de publication Web. La définition d’un itinéraire permanent n’entraîne pas la mise en route de l’ordinateur. Si la fonction de transfert IP n’est pas activée, l’ordinateur ne peut agir que pour diriger le trafic spécifique destiné à un autre réseau vers l’interface appropriée. Il s’agit essentiellement de définir deux passerelles, une comme la connexion par défaut aux réseaux externes, une pour le trafic destiné à l’interface interne et sur un routeur ou un autre réseau.<BR>Toutefois, la création d’itinéraires permanents pour tous les sous-réseaux peut ne pas être nécessaire si les routeurs de votre réseau sont configurés pour résumer les itinéraires. Créez un itinéraire permanent vers le réseau où le routeur est défini, puis utilisez le routeur comme passerelle par défaut. Si vous n’êtes pas sûr de la configuration de votre réseau et que vous avez besoin d’aide pour savoir quels itinéraires persistants doivent être créés, contactez les ingénieurs réseau de votre entreprise.<BR>Le proxy inverse doit être en mesure de résoudre les enregistrements d’hôte DNS (A) pour le directeur interne, le serveur frontal, et le FQDN du pool de sauts suivants utilisés dans les règles de publication Web. Comme pour des raisons de sécurité, il est recommandé de ne pas configurer un proxy inverse pour utiliser un serveur DNS situé dans le réseau interne. Cela signifie que vous avez besoin de serveurs DNS dans le périmètre ou que vous avez besoin d’entrées de fichier HOSTs sur le proxy inverse qui résout chacun de ces noms de domaine complets à l’adresse IP interne des serveurs.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>Pour configurer les cartes réseau sur l’ordinateur proxy inverse

1.  Sur Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 Server en tant que proxy inverse, ouvrez modifier les **paramètres** de la carte en cliquant sur **Démarrer**, pointez sur **panneau**de configuration, cliquez sur **réseau. et le centre de partage**, puis en cliquant sur **modifier les paramètres**de la carte.

2.  Cliquez avec le bouton droit sur la connexion réseau externe que vous souhaitez utiliser pour l’interface externe, puis cliquez sur **Propriétés**.

3.  Dans la page **Propriétés** , cliquez sur l’onglet **mise en réseau** , cliquez sur **protocole Internet version 4 (TCP/IPv4)** dans la liste **cette connexion utilise les éléments suivants** , puis cliquez sur **Propriétés**.

4.  Dans la page de **Propriétés du protocole Internet (TCP/IP)** , configurez les adresses IP en fonction du réseau de sous-réseau auquel la carte réseau est attachée.
    
    <div>
    

    > [!NOTE]  
    > Si le proxy inverse est déjà utilisé par d’autres applications qui utilisent HTTPs/TCP/443 (par exemple, pour la publication d’Outlook Web Access), vous devez ajouter une autre adresse IP pour pouvoir publier les services Web 2013 Lync Server sur HTTPs/TCP/443 sans interférer à l’aide des règles et des écouteurs Web existants, ou si vous avez besoin de remplacer le certificat existant par un certificat qui ajoute les nouveaux noms de domaine complets sur le nom de l’autre objet.

    
    </div>

5.  Cliquez sur **OK**, puis sur **OK**.

6.  Dans **connexions réseau**, cliquez avec le bouton droit sur la connexion réseau interne que vous souhaitez utiliser pour l’interface interne, puis cliquez sur **Propriétés**.

7.  Répétez les étapes 3 à 5 pour configurer la connexion réseau interne.

</div>

</div>

<span> </span>

</div>

</div>

</div>

