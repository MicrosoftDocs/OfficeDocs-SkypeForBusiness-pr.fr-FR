---
title: Configurer les itinéraires de fédération et le trafic multimédia
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
ms.openlocfilehash: 9fe341a2cb7f670ebf3b96206a3c3c9c3f5d05b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Configurer les itinéraires de fédération et le trafic multimédia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Une fois que vous avez effectué la migration vers votre pool pilote Lync Server 2013, vous devez effectuer la transition de l’itinéraire de Fédération de vos serveurs Edge Lync Server 2010 vers l’itinéraire de Fédération de vos serveurs Edge Lync Server 2013.

Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia de votre serveur Edge et directeur Lync Server 2010 vers votre serveur Edge Lync Server 2013, pour un déploiement sur un seul site.

<div>


> [!IMPORTANT]  
> La modification de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia nécessite de planifier le temps d’arrêt de la maintenance pour les serveurs Edge Lync Server 2013 et Lync Server 2010. Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption. Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale. Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance. Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence.



</div>

<div>


> [!IMPORTANT]  
> Si votre serveur Edge Lync Server 2010 hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures décrites dans cette section ne sont pas prises en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs de Lync Server 2010 vers Lync Server 2013, puis mettre hors service le serveur Edge Lync Server 2010 avant d’activer la Fédération sur le serveur Edge Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> Si votre Fédération XMPP est routée via un serveur Edge Lync Server 2013, les utilisateurs hérités de Lync Server 2010 ne seront pas en mesure de communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, les stratégies XMPP et les certificats ont été configuré, le partenaire fédéré XMPP a été configuré sur Lync Server 2013 et les entrées DNS ont été mises à jour.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013

1.  Sur le serveur frontal Lync Server 2013, ouvrez la topologie existante dans le générateur de topologie.

2.  Dans le volet gauche, accédez au nœud du site, situé directement sous **Lync Server**.

3.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.

4.  Dans le volet gauche, sélectionnez **Itinéraire de fédération**.

5.  Sous **attribution**de l’itinéraire de Fédération du site, désactivez la case à cocher **activer la Fédération SIP** pour désactiver l’itinéraire de Fédération via l’environnement Lync Server 2010 hérité.
    
    ![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")

6.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

7.  Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.

8.  Dans le menu **Action**, cliquez sur **Publier la topologie**.

9.  Cliquez sur **Suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** quand la publication est terminée.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant

1.  Dans le volet gauche, accédez au nœud **Lync Server 2010**, puis au nœud **Pool de serveurs Edge**.

2.  Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.

3.  Sélectionnez **Général** dans le volet gauche.

4.  Décochez la case **Activer la fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page.
    
    ![Modifier les propriétés, général, effacer la Fédération d’activation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifier les propriétés, général, effacer la Fédération d’activation")

5.  Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.

6.  Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

7.  Vérifiez que la fédération pour le serveur Edge hérité est désactivée.
    
    ![Générateur de topologies, pool Edge, Fédération désactivée](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Générateur de topologies, pool Edge, Fédération désactivée")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Pour configurer des certificats sur le serveur Edge Lync Server 2010

1.  Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité de Lync Server 2010.

2.  Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.

3.  Affectez le certificat externe de proxy d’accès à l’interface externe Lync Server 2013 du serveur Edge.

4.  Le certificat d’interface interne du serveur Edge Lync Server 2013 doit être demandé auprès d’une autorité de certification approuvée et affecté.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Pour changer l’itinéraire de fédération Lync Server 2010 pour utiliser un serveur Edge Lync Server 2013

1.  Dans le volet gauche du Générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.

2.  Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.

3.  Sélectionnez **Général** dans le volet gauche.

4.  Cochez la case **Activer la fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page.
    
    ![Boîte de dialogue Modifier les propriétés, page général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")

5.  Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.

6.  Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

7.  Vérifiez que **Fédération (port 5061)** est **Activé**.
    
    ![Générateur de topologies, pool de serveurs Edge, Fédération activée](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Générateur de topologies, pool de serveurs Edge, Fédération activée")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Pour mettre à jour le tronçon suivant de fédération du serveur Edge Lync Server 2013

1.  Dans le volet gauche du Générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.

3.  Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Lync Server 2013.
    
    ![Boîte de dialogue Modifier les propriétés, page tronçon suivant](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page tronçon suivant")

4.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

5.  Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server** .

6.  Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Pour configurer le chemin d’accès des médias sortants du serveur Edge Lync Server 2013

1.  À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Lync Server 2013** , puis au pool sous **serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.

2.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

3.  Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.
    
    ![Modifier les propriétés, général, associer un pool de serveurs Edge](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modifier les propriétés, général, associer un pool de serveurs Edge")

4.  Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.

5.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Pour activer la fédération du serveur Edge Lync Server 2013

1.  Dans le volet gauche du Générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.

2.  Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.
    
    <div>
    

    > [!NOTE]  
    > La Fédération ne peut être activée que pour un seul pool de serveurs Edge. Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur.

    
    </div>

3.  Dans la page **Général**, vérifiez que le paramètre **Activer la fédération pour ce pool Edge (port 5061)** est coché.
    
    ![Boîte de dialogue Modifier les propriétés, page général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")

4.  Cliquez sur **OK** pour fermer la page Modifier les propriétés.

5.  Naviguez ensuite vers le nœud du site.

6.  Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.

7.  Dans le volet gauche, cliquez sur **Itinéraire de fédération**.

8.  Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013 répertorié.
    
    ![Modifier les propriétés, page itinéraire de Fédération](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")

9.  Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.
    
    Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration du serveur Edge

1.  Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server** .

2.  Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.

3.  Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez voir le message suivant :<BR><STRONG>Attention : La topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire au cours d’une migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge voulu. Si vous voulez déployer plusieurs serveurs Edge de fédération de sorte qu’ils soient actifs simultanément (pas un scénario de migration, donc), vérifiez que tous les partenaires fédérés utilisent Lync Server. Vérifiez que l’enregistrement SRV DNS externe liste tous les serveurs Edge activés pour la fédération.</STRONG><BR>Cet avertissement est attendu et peut être ignoré en toute sécurité.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Pour configurer le serveur Edge Lync Server 2013

1.  Mettez tous les serveurs Edge Lync Server 2013 en ligne.

2.  Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’utilisez pas un équilibreur de charge matérielle, vous devez mettre à jour l’enregistrement A DNS pour que la fédération puisse résoudre le nouveau serveur Edge d’accès Lync Server. Pour ce faire, réduisez la valeur TLL pour le FQDN du serveur Edge d’accès Lync Server externe afin que lorsque le DNS est mis à jour pour pointer vers le nouveau serveur Edge d’accès Lync Server, la fédération et l’accès à distance soient mis à jour rapidement.

    
    </div>

3.  Ensuite, arrêtez le serveur **Edge d’accès Lync Server** à partir de chaque ordinateur serveur Edge.

4.  À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **Outils d’administration**.

5.  Dans la liste des services, trouvez **Serveur Edge d’accès Lync Server**.

6.  Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.

7.  Définissez le type de démarrage sur **Désactivé**.

8.  Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

