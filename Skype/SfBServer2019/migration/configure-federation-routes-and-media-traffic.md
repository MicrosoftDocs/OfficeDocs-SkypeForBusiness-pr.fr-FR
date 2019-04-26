---
title: Configuration des itinéraires de fédération et du trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’entreprises distinctes de communiquer au-delà des frontières du réseau. Après avoir migré vers votre pool pilote, vous devez transition à partir de l’itinéraire de fédération de vos serveurs Edge de versions antérieures à l’itinéraire de fédération de votre Skype pour les serveurs de périphérie 2019 Business Server.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238743"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configuration des itinéraires de fédération et du trafic multimédia

La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’entreprises distinctes de communiquer au-delà des frontières du réseau. Après avoir migré vers votre pool pilote, vous devez transition à partir de l’itinéraire de fédération de la version précédente serveurs de périphérie pour l’itinéraire de fédération de votre Skype pour les serveurs de périphérie 2019 Business Server.
  
Utilisez les procédures suivantes pour passer l’itinéraire de fédération et l’itinéraire de trafic multimédia de votre version précédente du serveur de transport Edge et directeur à votre Skype pour Business 2019 Edge Server, pour un déploiement de site unique.
  
> [!IMPORTANT]
> Modification de l’itinéraire de fédération et l’itinéraire de trafic multimédia nécessite que vous planifiez temps mort de maintenance pour le Skype pour Business Server 2019 et la version précédente de serveurs de périphérie. Ce processus toute transition signifie également que les accès fédéré n’est pas disponible pour la durée de la panne. Vous devez planifier le temps d’arrêt pendant une période donnée lorsque vous prévoyez une activité utilisateur minimale. Vous devez également fournir une notification suffisante à vos utilisateurs finaux. Planifier en conséquence, ce jeu de dépannage appropriées attentes au sein de votre organisation. 
  
> [!IMPORTANT]
> Si votre serveur Edge hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, service Edge de conférence Web et A / V Edge service, les procédures décrites dans cette section ne sont pas pris en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs, puis mettre hors service les serveur Edge de versions précédentes avant d’activer la fédération sur le Skype pour Business Server 2019 Edge Server. 
  
> [!IMPORTANT]
> Si la fédération XMPP est routée via un Skype pour le serveur de périphérie 2019 Business Server, les utilisateurs de la version précédente ne sera pas en mesure de communiquer avec les partenaires fédérés XMPP jusqu'à ce que tous les utilisateurs ont été déplacés vers Skype pour Business Server 2019, stratégies XMPP et les certificats qui ont été configurés, le partenaire fédéré XMPP a été configuré sur Skype pour Business Server 2019 et, enfin, les entrées DNS ont été mis à jour. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Pour supprimer l’association de fédération hérité de Skype pour les sites Business Server 2019

1. Sur Skype pour le serveur frontal Business Server 2019, ouvrez la topologie existante dans le Générateur de topologie. 
    
2. Dans le volet gauche, accédez au nœud du site, qui se trouve juste au-dessous **Skype pour Business Server**.
    
3. Cliquez sur le site, puis cliquez sur **Modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **itinéraire de fédération**. 
    
5. Sous **attribution itinéraire de fédération du Site**, désactivez la case à cocher **Activer la fédération SIP** pour désactiver l’itinéraire de fédération par le biais de l’ancien environnement. 
  
6. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
7. Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Skype pour Business Server**.
    
8. Dans le menu **Action** , cliquez sur **Publier la topologie**.
    
9. Cliquez sur **suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminée. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur Edge hérité comme un serveur Edge non fédéré

1. Dans le volet gauche, accédez au nœud installer hérité, puis au nœud **Edge pools** . 
    
2. Cliquez sur le serveur de périphérie, puis cliquez sur **Modifier les propriétés**.
    
3. Sélectionnez **Général** dans le volet gauche. 
    
4. Désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)** et cliquez sur **OK** pour fermer la page. 
  
5. Dans le menu **Action** , sélectionnez **Publier la topologie**, puis cliquez sur **suivant**.
    
6. Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer** pour fermer l’Assistant. 
    
7. Vérifiez que la fédération pour le serveur Edge hérité est désactivée dans le Générateur de topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Pour configurer des certificats sur le serveur Edge hérité

1. Exportez le certificat de Proxy d’accès externe, avec la clé privée, depuis le serveur Edge hérité. 
    
2. Sur le Skype pour Business Server 2019 Edge Server et l’importation du certificat externe du Proxy d’accès de l’étape précédente.
    
3. Affecter le certificat externe de Proxy d’accès à la Skype pour Business Server 2019, interface externe du serveur Edge.
    
4. Le certificat de l’interface interne de le Skype pour le serveur de périphérie 2019 Business Server doit être demandé à partir d’une autorité de certification approuvée et assigné. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Pour changer l’itinéraire de fédération de la version précédente pour utiliser Skype pour Business Server 2019 Edge Server

1. À partir du Générateur de topologie dans le volet gauche, accédez au nœud **Skype pour Business Server 2019** , puis le nœud **pools de serveurs Edge** . 
    
2. Cliquez sur le serveur de périphérie, puis cliquez sur **Modifier les propriétés**.
    
3. Sélectionnez **Général** dans le volet gauche. 
    
4. Activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page. 
  
5. Dans le menu **Action** , sélectionnez **Publier la topologie**, puis cliquez sur **suivant**.
    
6. Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer** pour fermer l’Assistant. 
    
7. Vérifiez que **fédération (port 5061)** est **activé** dans le Générateur de topologie.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Pour mettre à jour Skype pour le tronçon suivant de fédération Business Server 2019 Edge Server

1. À partir du Générateur de topologie dans le volet gauche, accédez au nœud **Skype pour Business Server 2019** , puis le nœud **pools de serveurs Edge** . 
    
2. Développez le nœud, cliquez sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**. 
    
3. Dans la page **Général** , sous **sélection du tronçon suivant**, sélectionnez le Skype pour Business Server 2019 pool dans la liste déroulante.
  
4. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
5. Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Skype pour Business Server**. 
    
6. Dans le menu **Action** , cliquez sur **Publier la topologie** et terminez l’Assistant. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Pour configurer Skype pour le chemin d’accès de serveur de périphérie Business Server 2019 sortant des médias

1. À partir du Générateur de topologie dans le volet gauche, naviguez jusqu’au nœud **Skype pour Business Server 2019** puis jusqu’au pool sous **Serveurs frontaux frontaux Standard Edition** ou **pools frontaux Enterprise Edition**.
    
2. Avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.
    
3. Dans la section **Associations** , activez la case à cocher **pool Edge associé (pour les composants multimédias)** . 
  
4. Dans la zone de liste déroulante, sélectionnez le Skype pour Business Server 2019 Edge Server.
    
5. Cliquez sur **OK** pour fermer la page **Modifier les propriétés** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Pour activer la fédération Business Server 2019 Edge Server Skype

1. À partir du Générateur de topologie dans le volet gauche, accédez au nœud **Skype pour Business Server 2019** , puis le nœud **pools de serveurs Edge** . 
    
2. Développez le nœud, cliquez sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**. 
    
    > [!NOTE]
    > Fédération ne peut pas être activée pour un seul pool Edge. Si vous avez plusieurs pools Edge, sélectionnez celle à utiliser en tant que le pool Edge fédéré. 
  
3. Dans la page **Général** , vérifiez que la case à cocher **Activer la fédération pour ce pool Edge (Port 5061)** est activée. 
  
4. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
5. Accédez au nœud du site. 
    
6. Cliquez sur le site, puis cliquez sur **Modifier les propriétés**.
    
7. Dans le volet gauche, cliquez sur **itinéraire de fédération**.
    
8. Sous **attribution itinéraire de fédération du Site**, sélectionnez **Activer la fédération SIP**, puis, dans la liste Sélectionnez le Skype pour Business Server 2019 Edge Server répertoriés. 
  
9. Cliquez sur **OK** pour fermer la page **Modifier les propriétés** . 
    
     Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration de serveur de transport Edge

1. Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Skype pour Business Server**. 
    
2. Dans le menu **Action** , sélectionnez **Publier la topologie** et terminez l’Assistant. 
    
3. Attendez que la réplication Active Directory se produise sur tous les pools dans le déploiement.
    
    > [!NOTE]
    > Vous pouvez voir le message suivant : **Avertissement : la topologie contient plusieurs serveurs de périphérie fédérés. Cela peut se produire durant la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait activement utilisé pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur de périphérie approprié. Si vous souhaitez déployer plusieurs fédération serveur Edge à active simultanément (c'est-à-dire, pas un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype pour Business Server. Vérifiez que l’enregistrement DNS SRV externe répertorie tous les serveurs de périphérie de fédération activée.** Cet avertissement est attendu et peut être ignoré en toute sécurité. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Pour configurer Skype pour Business Server 2019 Edge Server

1. Mettez tous le Skype pour les serveurs de périphérie 2019 Business Server en ligne. 
    
2. Mettre à jour les règles de routage pare-feu externe ou les paramètres d’équilibrage de charge matériel pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la fédération (généralement le port 5061) à la Skype pour le serveur Edge 2019 Business Server, au lieu du serveur Edge hérité.
    
    > [!NOTE]
    > Si vous ne disposez pas d’un mécanisme d’équilibrage de charge, vous devez mettre à jour l’enregistrement DNS A pour la fédération résoudre le nouveau Skype pour le serveur Edge d’accès serveur Business. Pour ce faire, avec une interruption minimale, diminuer la valeur TLL pour la Skype externe pour le nom de domaine complet Business serveur Access Edge afin que la mise à jour du DNS pour pointer vers le nouveau Skype pour Business serveur Edge d’accès, la fédération et accès à distance à jour rapidement. 
  
3. Arrêtez le **Skype pour le serveur Edge d’accès entreprise** à partir de chaque ordinateur serveur de périphérie. 
    
4. À partir de chaque ordinateur serveur de transport Edge hérité, ouvrez l’applet **Services** dans les **Outils d’administration**.
    
5. Dans la liste des services, recherchez **Skype pour Business serveur Edge d’accès**.
    
6. Le bouton droit sur les services, puis sélectionnez **Arrêter** pour arrêter le service. 
    
7. Définir le type de démarrage sur **désactivé**. 
    
8. Cliquez sur **OK** pour fermer la fenêtre **Propriétés** . 
    

