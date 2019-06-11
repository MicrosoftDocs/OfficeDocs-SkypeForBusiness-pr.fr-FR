---
title: 'Lync Server 2013 : Définition de la topologie Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Définition de la topologie Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Vous devez utiliser le générateur de topologie pour générer votre topologie et définir au moins un pool interne ou un serveur Standard Edition avant de pouvoir déployer votre serveur Edge. Utilisez la procédure suivante pour définir la topologie de bord d’un serveur Edge unique, puis utilisez les procédures décrites dans la rubriques [publier votre topologie dans Lync server 2013](lync-server-2013-publish-your-topology.md) et [exporter votre topologie Lync Server 2013 et copier celle-ci sur des éléments multimédias externes pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) . pour publier la topologie et la rendre accessible à votre serveur Edge.

<div>


> [!NOTE]  
> L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.



</div>

Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Vous pouvez également accorder des droits d’administrateur et des autorisations nécessaires pour ajouter des rôles de serveur à un compte d’utilisateur. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server. Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.

Si vous avez défini votre topologie de bord lorsque vous avez défini et publié votre topologie interne, et qu’aucune modification n’est requise pour la topologie de bord que vous avez précédemment définie, vous n’avez pas besoin de la définir et de la republier. Utilisez la procédure suivante uniquement si vous avez besoin d’apporter des modifications à votre topologie latérale. Vous devez rendre la topologie précédemment définie et publiée disponible pour vos serveurs Edge, en suivant la procédure décrite dans [exporter votre topologie Lync Server 2013 et la copier vers un média externe pour l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Vous ne pouvez pas exécuter le générateur de topologie à partir d’un serveur Edge. Vous devez l’exécuter à partir de votre serveur frontal ou des serveurs Standard Edition Server.



</div>

Le processus de définition de la topologie de votre serveur Edge est réalisé dans le générateur de topologie. Les trois principaux types de topologies de serveur Edge que vous planifiez et configurez sont les suivants:

  - Pour définir la topologie pour un serveur Edge unique

  - Pour définir la topologie d’un pool de serveurs Edge équilibré

  - Pour définir la topologie d’un pool de périphériques équilibrés de charge matérielle

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Pour définir la topologie pour un serveur Edge unique

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous voulez déployer un serveur Edge.

3.  Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle réserve de périphérie**.

4.  Dans **définir le nouveau pool**de bordures, cliquez sur **suivant**.

5.  Dans **définir le nom de domaine complet (FQDN) du pool Edge**, procédez comme suit:
    
      - Dans **nom**de domaine complet (FQDN) du pool, tapez le nom de domaine complet (FQDN) de l’interface interne du serveur Edge.
        
        <div>
        

        > [!IMPORTANT]  
        > Le nom spécifié doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom de l’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom court qui n’est pas un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine. Utilisez uniquement les caractères standard (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat). Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configurer la prise en charge de DNS pour les bords dans Lync Server 2013</A>.

        
        </div>
    
      - Cliquez sur **pool d’ordinateurs unique**, puis sur **suivant**.

6.  Dans **Sélectionner les fonctionnalités**, procédez comme suit:
    
      - Si vous envisagez d’utiliser un nom de domaine complet et une adresse IP uniques pour le service d’accès SIP, le service de conférence Web de Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** .
    
      - Si vous envisagez d’activer la Fédération, activez la case à cocher **activer la Fédération pour ce pool Edge (Port 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez sélectionner cette option, mais un seul pool de périphériques ou serveur de périphérie de votre organisation peut être publié en externe pour la Fédération. Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique. Par exemple, si votre déploiement inclut un pool de périphérie ou un serveur Edge unique déployé à New York et un serveur déployé à Londres et que vous activez la prise en charge de la Fédération sur le pool de périphériques de la Nouvelle-York ou sur un serveur de périphérie Pool Edge ou serveur Edge unique. Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

        
        </div>
    
      - Si vous envisagez de prendre en charge le protocole de messagerie et de présence extensible (XMPP) pour votre déploiement, activez la case à cocher **activer la Fédération XMPP (port 5269)** .

7.  Dans **Sélectionner les options IP**, procédez comme suit:
    
      - **Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques
    
      - **Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques
    
      - **Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques
    
      - **Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques
    
    Vous pouvez également configurer le serveur de périphérie ou le pool Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **l’adresse IP externe de ce pool Edge est traduite par tar**.

8.  Dans les noms de **domaine complets externes**, procédez comme suit:
    
      - Si vous avez choisi de **Sélectionner les fonctionnalités** que vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge a/V, tapez le nom de domaine complet dans **accès SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si vous choisissez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés: 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence Web et 443 pour service Edge A/V). La sélection de cette option permet d’éviter les problèmes de connectivité potentiels et de simplifier la configuration, car vous pouvez ensuite utiliser le même numéro de port (par exemple, 443) pour les trois services.

        
        </div>
    
      - Si vous n’avez pas choisi d’utiliser une adresse de domaine complet et un nom de domaine complet (FQDN) dans **Select** , tapez les noms de domaine complets externes pour l' **accès SIP**, les **conférences Web** et la **vidéo audio**, en conservant les ports par défaut.

9.  Cliquez sur **Suivant**.

10. Dans **définir l’adresse IP interne**, tapez l’adresse IP de votre serveur Edge dans **adresse IPv4 interne** et **adresse IPv6 interne** , en fonction de vos besoins. Cliquez sur **Suivant**.

11. Dans **définir l’adresse IP externe**, procédez comme suit:
    
      - Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IPv4 externe du serveur Edge dans **accès SIP**, puis cliquez sur **suivant**.
    
      - Si vous avez choisi d’utiliser les adresses IPv6, tapez l’adresse IPv6 externe du serveur Edge dans **accès SIP**, puis cliquez sur **suivant**.
    
      - Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez les adresses IPv4 externes du serveur Edge dans **accès SIP**, **conférences Web**et **conférences a/v**, puis Cliquez sur **suivant**.
    
      - Si vous avez choisi d’utiliser les adresses IPv6 et que vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez les adresses IPv6 externes du serveur Edge dans **accès SIP**, **conférences Web**et **a/ V Conferencing**, puis cliquez sur **suivant**.
        
        <div>
        

        > [!NOTE]  
        > Si vous n’avez pas choisi d’activer et d’affecter l’adressage IPv6, cette boîte de dialogue ne s’affiche pas.

        
        </div>

12. Si vous choisissez d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **adresse IPv4 publique pour le service Edge A/V**, tapez l’adresse IPv4 publique à traduire par tar, puis cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

    
    </div>

13. Si vous choisissez d’utiliser des adresses NAT et IPv6, une boîte de dialogue s’affiche. Dans **adresse IPv6 publique pour le service Edge A/V**, tapez l’adresse IPv6 publique à traduire par tar, puis cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du service Edge A/V.

    
    </div>

14. Dans **définir le saut suivant**, dans le **pool de sauts suivant**, sélectionnez le nom du pool interne, qui peut être un pool frontal ou un pool Standard Edition. Si votre déploiement inclut un directeur, sélectionnez le réalisateur. Ensuite, cliquez sur **suivant**.

15. Dans la zone associer des regroupements **front-end**, spécifiez un ou plusieurs pools internes, qui peuvent inclure des pools frontaux et des serveurs Standard Edition, à associer à ce serveur Edge, en sélectionnant les noms des pools internes pour lesquels utiliser ce serveur Edge. communication avec des utilisateurs externes pris en charge.
    
    <div>
    

    > [!NOTE]  
    > Il n’est possible d’associer qu’un seul pool Edge équilibré ou un seul serveur Edge à chaque pool interne pour le trafic A/V. Si vous disposez déjà d’un pool interne associé à un serveur Edge ou à un pool de bords, un message d’avertissement s’affiche, indiquant que le pool interne est déjà associé à un serveur Edge ou à un serveur Edge. Si vous sélectionnez un pool déjà associé à un autre serveur Edge, l’Association est modifiée.

    
    </div>

16. Cliquez sur **Terminer**.

17. Publiez votre topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Pour définir la topologie d’un pool de serveurs Edge équilibré de charge DNS

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous voulez déployer des serveurs Edge.

3.  Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle réserve de périphérie**.

4.  Dans **définir le nouveau pool**de bordures, cliquez sur **suivant**.

5.  Dans **définir le nom de domaine complet (FQDN) du pool Edge**, procédez comme suit:
    
      - Dans **nom**de domaine complet (FQDN) du pool, tapez le nom de domaine complet (FQDN) de votre connexion interne.
        
        <div>
        

        > [!IMPORTANT]  
        > Le nom que vous spécifiez pour le pool doit correspondre au nom du pool de bords internes. Cette opération doit être définie en tant que nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Utilisez uniquement les caractères standard (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat).

        
        </div>
    
      - Cliquez sur **plusieurs pools d’ordinateurs**, puis cliquez sur **suivant**.

6.  Dans **Sélectionner les fonctionnalités**, procédez comme suit:
    
      - Si vous envisagez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web Lync Server 2013 et les services Edge A/V, activez la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** .
    
      - Si vous envisagez d’activer la Fédération, activez la case à cocher **activer la Fédération pour ce pool Edge (Port 5061)** . Cliquez sur **suivant** .
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez sélectionner cette option, mais un seul pool de périphériques ou serveur de périphérie de votre organisation peut être publié en externe pour la Fédération. Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou sur le serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou par le serveur Edge unique de New York. Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

        
        </div>
    
      - Si vous envisagez de prendre en charge le protocole de messagerie et de présence extensible (XMPP) pour votre déploiement, activez la case à cocher **activer la Fédération XMPP (port 5269)** .

7.  Cliquez sur **Suivant**.

8.  Dans **Sélectionner les options IP**, procédez comme suit:
    
      - **Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques
    
      - **Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques
    
      - **Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques
    
      - **Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques
    
    Vous pouvez également configurer le serveur de périphérie ou le pool Edge pour utiliser une adresse de traduction d’adresses réseau pour les adresses IP externes. Pour ce faire, activez la case à cocher **l’adresse IP externe de ce pool Edge est traduite par tar**.

9.  Dans les noms de **domaine complets externes**, procédez comme suit:
    
      - Si vous avez choisi de **Sélectionner les fonctionnalités** que vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge a/V, tapez le nom de domaine complet dans **accès SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si vous choisissez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés: 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence Web et 443 pour service Edge A/V). En sélectionnant cette option, vous pouvez éviter les problèmes de connectivité potentiels et simplifier la configuration, car vous pouvez ensuite utiliser le même numéro de port (par exemple, 443) pour les trois services.

        
        </div>
    
      - Si vous n’avez pas choisi d’utiliser une adresse de domaine complet et un nom de domaine complet (FQDN) dans **Sélectionner les fonctionnalités** , tapez le nom de domaine complet (FQDN) du pool pour l' **accès SIP**. Dans **conférences Web**, tapez le nom de domaine complet que vous avez choisi pour le côté public du pool de périphérie. Dans **audio/vidéo**, tapez le nom de domaine complet (FQDN) que vous avez choisi pour le côté public du pool Edge. Utiliser les ports par défaut.

10. Cliquez sur **Suivant**.

11. Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**.

12. Dans **FQDN et adresse IP internes**, procédez comme suit:
    
      - Dans **adresse IPv4 interne**, tapez l’adresse IPv4 et l' **adresse IPv6 interne** , en fonction de vos besoins pour le premier serveur de périmètre que vous voulez créer dans ce pool.
    
      - Dans **nom de domaine complet (FQDN) interne**, tapez le nom de domaine complet (FQDN) du premier serveur Edge que vous voulez créer dans ce pool.
        
        <div>
        

        > [!NOTE]  
        > Le nom de domaine complet spécifié doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine. Utilisez uniquement les caractères standard (y compris A – Z, a-z, 0 à 9 et les traits d’Union) lorsque vous attribuez des noms de domaine complets de vos serveurs Lync, serveurs de périphérie, groupes et matrices. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat). Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir <A href="lync-server-2013-configure-dns-for-edge-support.md">configurer la prise en charge de DNS pour les bords dans Lync Server 2013</A>.

        
        </div>

13. Cliquez sur **Suivant**.

14. Dans **définir les adresses IP externes**, procédez comme suit:
    
      - Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IP externe du serveur Edge dans **accès SIP**.
    
      - Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**. Dans **conférence Web**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge. Dans le cadre de **conférences A/V**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge.

15. Cliquez sur **Suivant**.

16. Si vous choisissez d’activer les adresses IPv6, dans **définir les adresses IP externes**, procédez comme suit:
    
      - Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans l' **accès SIP**.
    
      - Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**. Dans **conférence Web**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge. Dans le cadre de **conférences A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas choisi d’activer et d’affecter l’adressage IPv6, cette boîte de dialogue ne s’affiche pas.

    
    </div>

17. Cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Le premier serveur Edge que vous avez créé dans votre pool apparaît désormais dans la boîte de dialogue <STRONG>définir les ordinateurs dans ce pool</STRONG> .

    
    </div>

18. Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur de périmètre que vous voulez ajouter à votre liste de serveurs de bord.

19. Après avoir répété les étapes 11 à 14, cliquez sur **suivant** dans **définir les ordinateurs dans ce pool**.
    
    <div>
    

    > [!NOTE]  
    > À ce stade, vous pouvez voir les deux serveurs de périphérie de votre liste.

    
    </div>

20. Si vous choisissez d’utiliser la traduction d’adresses réseau (NAT), une boîte de dialogue s’affiche. Dans **adresse IP publique**, tapez les adresses publiques IPv4 et IPv6 (le cas échéant) à traduire par tar, puis cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > Il doit s’agir de l’adresse IP externe du bord A/V.

    
    </div>

21. Dans **définir le tronçon suivant**, dans la liste **pool de sauts suivants** , sélectionnez le nom du pool interne, qui peut être un pool frontal ou un pool Standard Edition. Si votre déploiement inclut un réalisateur, sélectionnez le nom du réalisateur. Ensuite, cliquez sur **suivant**.

22. Dans la liste de serveurs **Associate**, spécifiez un ou plusieurs pools internes, qui peuvent inclure des pools frontaux et des serveurs Standard Edition, à associer à ce serveur Edge, en sélectionnant les noms du ou des pools d’édition standard pour lesquels utiliser ce serveur Edge pour communication avec des utilisateurs externes pris en charge.
    
    <div>
    

    > [!NOTE]  
    > Il n’est possible d’associer qu’un seul pool Edge équilibré ou un seul serveur Edge à chaque pool interne pour le trafic A/V. Si vous disposez déjà d’un pool interne associé à un serveur Edge ou à un pool de bords, un message d’avertissement s’affiche, indiquant que le pool interne est déjà associé à un serveur Edge ou à un serveur Edge. Si vous sélectionnez un pool déjà associé à un autre serveur Edge, l’Association est modifiée.

    
    </div>

23. Cliquez sur **Terminer**.

24. Publiez votre topologie.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Pour définir la topologie d’un pool de serveurs Edge équilibré en charge matérielle

1.  Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site dans lequel vous voulez déployer des serveurs Edge.

3.  Cliquez avec le bouton droit sur pools de **bords**, puis sélectionnez **nouvelle liste de bord**.

4.  Dans **définir le nouveau pool**de bordures, cliquez sur **suivant**.

5.  Dans **définir le nom de domaine complet (FQDN) du pool Edge**, procédez comme suit:
    
      - Dans **FQDN**, tapez le nom de domaine complet (FQDN) que vous avez choisi pour le côté interne du pool de périphérie.
        
        <div>
        

        > [!IMPORTANT]  
        > Le nom que vous spécifiez pour le pool doit correspondre au nom du pool de bords internes. Cette opération doit être définie en tant que nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Utilisez uniquement les caractères standard (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le FQDN doit être attribué à l’SN dans le certificat).

        
        </div>
    
    <!-- end list -->
    
      - Cliquez sur **plusieurs pools d’ordinateurs**, puis sur **suivant**.

6.  Dans **Sélectionner les fonctionnalités** , effectuez les opérations suivantes:
    
      - Si vous envisagez d’utiliser un nom de domaine complet et une adresse IP uniques pour le service d’accès SIP, le service de conférence Web Lync Server et le service Edge A/V, activez la case à cocher **utiliser un nom de domaine complet & adresse IP** .
    
      - Si vous envisagez d’activer la Fédération, activez la case à cocher **activer la Fédération pour ce pool Edge (Port 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Vous pouvez sélectionner cette option, mais il se peut que vous n’ayez publié qu’une seule grappe de périphériques ou qu’un serveur Edge au sein de votre organisation pour la Fédération. Tout accès par des utilisateurs fédérés, y compris des utilisateurs de la messagerie instantanée publique, passe par le même pool de périphérie ou serveur à périphérie unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou sur le serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou par le serveur Edge unique de New York. Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

        
        </div>
    
      - Si vous envisagez de prendre en charge le protocole de messagerie et de présence extensible (XMPP) pour votre déploiement, activez la case à cocher **activer la Fédération XMPP (port 5269)** .

7.  Cliquez sur **Suivant**.

8.  Dans **Sélectionner les options IP**, procédez comme suit:
    
      - **Activer IPv4 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface interne du serveur Edge ou du pool de périphériques
    
      - **Activer IPv6 sur l’interface interne**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface interne du serveur Edge ou du pool de périphériques
    
      - **Activer IPv4 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv4 à l’interface externe du serveur Edge ou du pool de périphériques
    
      - **Activer IPv6 sur une interface externe**: activez la case à cocher si vous voulez appliquer une adresse IPv6 à l’interface externe du serveur Edge ou du pool de périphériques
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Ne cochez pas</STRONG> la case <STRONG>l’adresse IP externe de la liste des bords est traduite par tar</STRONG> . La traduction d’adresses réseau (NAT) n’est pas prise en charge lorsque vous utilisez l’équilibrage de charge matérielle.

    
    </div>

9.  Dans les noms de **domaine complets externes**, procédez comme suit:
    
      - Si vous avez choisi de **Sélectionner les fonctionnalités** que vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge a/V, tapez le nom de domaine complet dans **accès SIP**.
        
        <div>
        

        > [!NOTE]  
        > Si vous choisissez d’activer cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port recommandés: 5061 pour le service Edge d’accès, 444 pour le service Edge de conférence Web et 443 pour service Edge A/V). En sélectionnant cette option, vous pouvez éviter les problèmes de connectivité potentiels et simplifier la configuration, car vous pouvez ensuite utiliser le même numéro de port (par exemple, 443) pour les trois services.

        
        </div>
    
      - Si vous n’avez pas choisi d’utiliser une adresse de domaine complet et un nom de domaine complet (FQDN) dans **Sélectionner les fonctionnalités** , tapez le nom de domaine complet (FQDN) du pool pour l' **accès SIP**. Dans **conférences Web**, tapez le nom de domaine complet que vous avez choisi pour le côté public du pool de périphérie. Dans **audio/vidéo**, tapez le nom de domaine complet (FQDN) que vous avez choisi pour le côté public du pool Edge. Utiliser les ports par défaut.
        
        <div>
        

        > [!NOTE]  
        > Il s’agira des noms de domaine complets de l’adresse IP virtuelle pour le pool.

        
        </div>

10. Cliquez sur **Suivant**.

11. Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**.

12. Dans **définir les adresses IP externes**, procédez comme suit:
    
      - Si vous avez choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse **** IPv4 externe du serveur Edge dans accès SIP. ****
    
      - Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**. Dans **conférence Web**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge. Dans le cadre de **conférences A/V**, tapez l’adresse IP que vous avez choisie pour le côté public de ce serveur de pool Edge.

13. Cliquez sur **Suivant**.

14. Si vous choisissez d’activer les adresses IPv6, dans **définir les adresses IP externes**, procédez comme suit:
    
      - Si vous choisissez d’utiliser un nom de domaine complet et une adresse IP uniques pour l’accès SIP, le service de conférence Web et le service Edge A/V, tapez l’adresse IPv6 externe du serveur Edge dans l' **accès SIP**.
    
      - Si vous n’avez pas choisi d’utiliser un nom de domaine complet et une adresse IP uniques pour les services d’accès SIP, de service de conférence Web et de conférence A/V, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge pour l' **accès SIP**. Dans **conférence Web**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge. Dans le cadre de **conférences A/V**, tapez l’adresse IPv6 que vous avez choisie pour le côté public de ce serveur de pool Edge.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas choisi d’activer et d’affecter l’adressage IPv6, cette boîte de dialogue ne s’affiche pas.

    
    </div>

15. Cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Le premier serveur Edge que vous avez créé dans votre pool apparaît désormais dans la boîte de dialogue <STRONG>définir les ordinateurs dans ce pool</STRONG> .

    
    </div>

16. Dans **définir les ordinateurs dans ce pool**, cliquez sur **Ajouter**, puis répétez les étapes 11 à 14 pour le deuxième serveur de périmètre que vous voulez ajouter à votre pool de périphériques.

17. Après avoir répété les étapes 11 à 14, cliquez sur **suivant** dans **définir les ordinateurs dans ce pool**.
    
    <div>
    

    > [!NOTE]  
    > À ce stade, vous pouvez voir les deux serveurs de périphérie de votre liste.

    
    </div>

18. Dans **définir le tronçon suivant**, dans la liste **pool de sauts suivants** , sélectionnez le nom du pool interne, qui peut être un pool frontal ou un pool Standard Edition. Si votre déploiement inclut un réalisateur, sélectionnez le nom du réalisateur. Ensuite, cliquez sur **suivant**.

19. Dans la liste de serveurs **Associate**, spécifiez un ou plusieurs pools internes, qui peuvent inclure des pools frontaux et des serveurs Standard Edition, à associer à ce serveur Edge, en sélectionnant les noms du ou des pools d’édition standard pour lesquels utiliser ce serveur Edge pour communication avec des utilisateurs externes pris en charge.
    
    <div>
    

    > [!NOTE]  
    > Il n’est possible d’associer qu’un seul pool Edge équilibré ou un seul serveur Edge à chaque pool interne pour le trafic A/V. Si vous disposez déjà d’un pool interne associé à un serveur Edge ou à un pool de bords, un message d’avertissement s’affiche, indiquant que le pool interne est déjà associé à un serveur Edge ou à un serveur Edge. Si vous sélectionnez un pool déjà associé à un autre serveur Edge, l’Association est modifiée.

    
    </div>

20. Cliquez sur **Terminer**.

21. Publiez votre topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

