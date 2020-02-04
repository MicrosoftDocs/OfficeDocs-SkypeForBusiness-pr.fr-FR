---
title: Configuration des itinéraires de fédération et du trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Configuration des itinéraires de fédération et du trafic multimédia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau. Après avoir effectué une migration vers votre pool de pilotes de Lync Server 2013, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs Edge Lync Server 2010 vers l’itinéraire de Fédération de votre serveur Edge Lync Server 2013.

Pour effectuer un déploiement sur un site, procédez comme suit pour migrer l’itinéraire de la Fédération et l’itinéraire de trafic multimédia de votre serveur Edge et de votre directeur 2010 Lync Server 2013 vers votre serveur Edge Lync Server.

<div>


> [!IMPORTANT]  
> La modification de l’itinéraire et de l’itinéraire de trafic multimédia requis pour la planification de la maintenance pour les serveurs Edge Lync Server 2013 et Lync Server 2010. Ce processus de transition complet signifie également que l’accès fédéré ne sera pas disponible pendant la durée de la période d’interruption. Nous vous conseillons de planifier le temps d’arrêt à un moment où vous vous attendez à un minimum d’activités utilisateur. Vous devez également fournir une notification suffisante à vos utilisateurs finaux. Planifiez en conséquence pour cette interruption et définissez les attentes appropriées au sein de votre organisation.



</div>

<div>


> [!IMPORTANT]  
> Si votre serveur Edge Lync Server 2010 hérité est configuré de manière à utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez tout d’abord migrer tous vos utilisateurs de Lync Server 2010 vers Lync Server 2013, puis désactivez le serveur Edge Lync Server 2010 avant d’activer la Fédération sur le serveur Edge Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Si votre Fédération XMPP est routée via un serveur Edge Lync Server 2013, les utilisateurs hérités de Lync Server 2010 ne seront pas en mesure de communiquer avec le partenaire fédéré de XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, que les stratégies et les certificats XMPP configuré, le partenaire fédéré de XMPP a été configuré sur Lync Server 2013, et la mise à jour des entrées DNS.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013

1.  Sur le serveur frontal Lync Server 2013, ouvrez la topologie existante dans le générateur de topologie.

2.  Dans le volet gauche, accédez au nœud de site qui se trouve juste en dessous de **Lync Server**.

3.  Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.

4.  Dans le volet gauche, sélectionnez **gamme de Fédération**.

5.  Sous **affectation**de l’itinéraire de Fédération de site, décochez la case **activer la Fédération SIP** pour désactiver le routage de Fédération par le biais de l’environnement 2010 hérité de Lync Server.
    
    ![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")

6.  Cliquez sur **OK** pour fermer la page modifier les propriétés.

7.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync**.

8.  Dans le menu **action** , cliquez sur **publier la topologie**.

9.  Cliquez sur **suivant** pour finaliser le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminé.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur de périphérie traditionnel en tant que serveur Edge non fédéré

1.  Dans le volet gauche, accédez au nœud **Lync Server 2010** , puis au nœud **pools de bords** .

2.  Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **modifier les propriétés**.

3.  Dans le volet gauche, sélectionnez **général** .

4.  Décochez la case **activer la Fédération pour ce pool Edge (port 5061)** , puis sélectionnez **OK** pour fermer la page.
    
    ![Modifier les propriétés, général, effacer la Fédération d’activation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifier les propriétés, général, effacer la Fédération d’activation")

5.  Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.

6.  Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.

7.  Vérifiez que la Fédération pour le serveur de périphérie antérieur est désactivée.
    
    ![Générateur de topologie, pool de périphériques, Fédération désactivé](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Générateur de topologie, pool de périphériques, Fédération désactivé")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Pour configurer des certificats sur le serveur Edge Lync Server 2010

1.  Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Lync Server 2010 hérité.

2.  Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.

3.  Attribuez le certificat externe du proxy d’accès à l’interface externe de Lync Server 2013 du serveur Edge.

4.  Le certificat d’interface interne du serveur Edge Lync Server 2013 doit être demandé auprès d’une autorité de certification approuvée et attribué.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Pour modifier l’itinéraire de Fédération de Lync Server 2010 de sorte qu’il utilise Lync Server 2013 Edge Server

1.  Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Lync Server 2013** , puis au nœud **pools de périphérie** .

2.  Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **modifier les propriétés**.

3.  Dans le volet gauche, sélectionnez **général** .

4.  Sélectionnez l’entrée de la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** , puis cliquez sur **OK** pour fermer la page.
    
    ![Boîte de dialogue Modifier les propriétés, page général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")

5.  Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.

6.  Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.

7.  Vérifier la **Fédération (le port 5061)** est défini sur **activé**.
    
    ![Générateur de topologie, pool de périphériques, Fédération activée](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Générateur de topologie, pool de périphériques, Fédération activée")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Pour mettre à jour Lync Server 2013 Edge Server Federation Next hop

1.  Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Lync Server 2013** , puis au nœud **pools de périphérie** .

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**.

3.  Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Lync Server 2013.
    
    ![Boîte de dialogue Modifier les propriétés, page saut suivant](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page saut suivant")

4.  Cliquez sur **OK** pour fermer la page modifier les propriétés.

5.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync** .

6.  Dans le menu **action** , cliquez sur **publier la topologie** et terminer l’Assistant.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Pour configurer le chemin multimédia sortant du serveur Lync Server 2013 Edge

1.  Dans le concepteur de topologies, dans le volet de gauche, accédez au nœud **Lync Server 2013** , puis au pool sous **Standard Edition serveurs front end** ou **Enterprise Edition**.

2.  Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

3.  Dans la section **associations** , activez la case à cocher **associer le pool Edge (pour les composants multimédias)** .
    
    ![Modification des propriétés, général et pool de périphérie](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modification des propriétés, général et pool de périphérie")

4.  Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.

5.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Pour activer la Fédération de serveur Edge Lync Server 2013

1.  Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Lync Server 2013** , puis au nœud **pools de périphérie** .

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**.
    
    <div>
    

    > [!NOTE]  
    > La Fédération ne peut être activée que pour un seul pool de bords. Si vous avez plusieurs pools de bords, sélectionnez-en un pour les utiliser comme pools de frontière de Fédération.

    
    </div>

3.  Dans la page **général** , assurez-vous que le paramètre **activer la Fédération pour ce pool Edge (port 5061)** est coché.
    
    ![Boîte de dialogue Modifier les propriétés, page général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")

4.  Cliquez sur **OK** pour fermer la page modifier les propriétés.

5.  Ensuite, accédez au nœud site.

6.  Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.

7.  Dans le volet de gauche, cliquez sur **route de Fédération**.

8.  Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013.
    
    ![Modifier les propriétés, page itinéraire de Fédération](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")

9.  Cliquez sur **OK** pour fermer la page **modifier les propriétés** .
    
    Pour les déploiements multisites, procédez comme suit sur chaque site.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration de serveur Edge

1.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync** .

2.  Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant.

3.  Attendez la fin de la réplication Active Directory pour tous les pools du déploiement.
    
    <div>
    

    > [!NOTE]  
    > Le message suivant risque de s’afficher :<BR><STRONG>AVERTISSEMENT : la topologie comporte plus d’un serveur Edge fédéré. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous voulez déployer plusieurs serveurs de périphérie de Fédération de manière à être actifs dans le cadre de la migration (autrement dit, qu’il ne s’agit pas d’un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Lync Server. Vérifiez que l’enregistrement SRV DNS externe recense tous les serveurs Edge compatibles avec la Fédération.</STRONG><BR>Cet avertissement est attendu et peut être ignoré en toute sécurité.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Pour configurer Lync Server 2013 Edge Server

1.  Accédez à tous les serveurs Edge Lync Server 2013 en ligne.

2.  Mettez à jour les règles de routage de pare-feu externe ou les paramètres de l’équilibrage de charge matérielle pour envoyer le trafic SIP pour l’accès externe (en général, le port 443) et la Fédération (en général, le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas d’équilibrage de charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération pour résoudre le nouveau serveur Lync Server Access Edge. Pour effectuer cette opération avec un minimum de perturbation, réduisez la valeur TLL du nom de domaine complet (FQDN) du périmètre Lync Server de Lync Server de façon à ce qu’elle pointe vers le nouveau serveur Lync Server d’accès.

    
    </div>

3.  Ensuite, arrêtez le **Edge d’accès de Lync Server** depuis chaque ordinateur du serveur Edge.

4.  À partir de chaque ordinateur serveur Edge hérité, ouvrez l’application **services** à partir des **Outils d’administration**.

5.  Dans la liste services, recherchez **Edge Access Server**.

6.  Cliquez avec le bouton droit sur le nom des services, puis sélectionnez **arrêter** pour arrêter le service.

7.  Définissez le type de démarrage sur **désactivé**.

8.  Cliquez sur **OK** pour fermer la fenêtre **Propriétés** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

