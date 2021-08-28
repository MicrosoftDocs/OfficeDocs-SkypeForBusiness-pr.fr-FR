---
title: Configurer les itinéraires de fédération et le trafic multimédia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Après avoir migré vers votre pool pilote, vous devez passer de l’itinéraire de fédération de vos serveurs Edge de versions précédentes à l’itinéraire de fédération de vos serveurs Edge Skype Entreprise Server 2019.
ms.openlocfilehash: f051321667e12a468df1186147f6fab1d7bbe5cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613403"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurer les itinéraires de fédération et le trafic multimédia

La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Après avoir migré vers votre pool pilote, vous devez passer de l’itinéraire de fédération des serveurs Edge de votre version précédente à l’itinéraire de fédération de vos serveurs Edge Skype Entreprise Server 2019.
  
Utilisez les procédures suivantes pour faire passer l’itinéraire de fédération et l’itinéraire de trafic multimédia du serveur Edge et du directeur de votre version précédente vers votre serveur Edge Skype Entreprise Server 2019, pour un déploiement sur un seul site.
  
> [!IMPORTANT]
> La modification de l’itinéraire de fédération et de l’itinéraire de trafic multimédia nécessite la planification d’un temps d’arrêt de maintenance pour les serveurs Edge Skype Entreprise Server 2019 et versions antérieures. Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption. Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale. Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance. Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence. 
  
> [!IMPORTANT]
> Si votre serveur Edge hérité est configuré pour utiliser le même nom de groupe pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section ne sont pas pris en charge. Si les services Edge hérités sont configurés pour utiliser le même nom de groupe, vous devez d’abord migrer tous vos utilisateurs, puis désaffecter les versions précédentes du serveur Edge avant d’activer la fédération sur le serveur Edge Skype Entreprise Server 2019. 
  
> [!IMPORTANT]
> Si votre fédération XMPP est acheminée via un serveur Edge Skype Entreprise Server 2019, les utilisateurs de la version précédente ne pourront pas communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Skype Entreprise Server 2019, que les stratégies et certificats XMPP ont été configurés, que le partenaire fédéré XMPP a été configuré sur Skype Entreprise Server 2019 et que, enfin, les entrées DNS ont été mises à jour. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Pour supprimer l’association de fédération héritée Skype Entreprise Server sites 2019

1. Sur le Skype Entreprise Server frontal 2019, ouvrez la topologie existante dans le Générateur de topologies. 
    
2. Dans le volet gauche, accédez au nœud de site, qui se trouve juste en dessous de **Skype Entreprise Server**.
    
3. Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **Itinéraire de fédération**. 
    
5. Sous **Affectation de l’itinéraire de** fédération du site, **désactivez** la case à cocher Activer la fédération SIP pour désactiver l’itinéraire de fédération via l’environnement hérité. 
  
6. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
7. Dans **le Générateur de topologie,** sélectionnez le nœud supérieur **Skype Entreprise Server**.
    
8. Dans le menu **Action**, cliquez sur **Publier la topologie**.
    
9. Cliquez **sur Suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** une fois le processus de publication terminé. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant

1. Dans le volet gauche, accédez au nœud d’installation hérité, puis au nœud **pools edge.** 
    
2. Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.
    
3. Sélectionnez **Général** dans le volet gauche. 
    
4. Activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page. 
  
5. Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.
    
6. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer. 
    
7. Vérifiez que la fédération pour le serveur Edge hérité est désactivée dans le Générateur de topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Pour configurer des certificats sur le serveur Edge hérité

1. Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité. 
    
2. Sur le serveur Edge Skype Entreprise Server 2019 et importez le certificat externe du proxy d’accès à partir de l’étape précédente.
    
3. Affectez le certificat externe du proxy d’accès Skype Entreprise Server interface externe 2019 du serveur Edge.
    
4. Le certificat d’interface interne du serveur Edge Skype Entreprise Server 2019 doit être demandé à une ca de confiance et affecté. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Pour modifier l’itinéraire de fédération de la version précédente Skype Entreprise Server serveur Edge 2019

1. À partir du Générateur de topologie, dans le volet gauche, accédez au nœud **Skype Entreprise Server 2019,** puis au nœud **pools edge.** 
    
2. Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.
    
3. Sélectionnez **Général** dans le volet gauche. 
    
4. Activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061),** puis cliquez sur **OK** pour fermer la page. 
  
5. Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.
    
6. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer. 
    
7. Vérifiez que **la fédération (port 5061)** est définie sur **Activé dans** le Générateur de topologie.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Pour mettre à Skype Entreprise Server le saut suivant de fédération du serveur Edge 2019

1. À partir du Générateur de topologie, dans le volet gauche, accédez au nœud **Skype Entreprise Server 2019,** puis au nœud **pools edge.** 
    
2. Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**. 
    
3. Dans la page **Général,** sous Sélection du **saut suivant,** sélectionnez dans la liste Skype Entreprise Server pool 2019.
  
4. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
5. Dans **le Générateur de topologie,** sélectionnez le nœud supérieur **Skype Entreprise Server**. 
    
6. Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Pour configurer Skype Entreprise Server chemin d’accès multimédia sortant du serveur Edge 2019

1. À partir du Générateur de topologie, dans le volet gauche, accédez au nœud **Skype Entreprise Server 2019,** puis au pool sous **Édition Standard Serveurs** frontux ou pools frontux **Êdition Entreprise.**
    
2. Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.
    
3. Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**. 
  
4. Dans la zone de drop-down, sélectionnez Skype Entreprise Server serveur Edge 2019.
    
5. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Pour activer la Skype Entreprise Server serveur Edge 2019

1. À partir du Générateur de topologie, dans le volet gauche, accédez au nœud **Skype Entreprise Server 2019,** puis au nœud **pools edge.** 
    
2. Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**. 
    
    > [!NOTE]
    > La fédération ne peut être activée que pour un seul pool edge. Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur. 
  
3. Dans la page **Général,** vérifiez que la case à cocher Activer la fédération pour ce **pool Edge (port 5061)** est activée. 
  
4. Cliquez sur **OK** pour fermer la page Modifier les propriétés. 
    
5. Accédez au nœud de site. 
    
6. Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.
    
7. Dans le volet gauche, cliquez sur **Itinéraire de fédération**.
    
8. Sous **Affectation de l’itinéraire** de fédération du site, sélectionnez Activer la fédération **SIP,** puis, dans la liste, sélectionnez le serveur Edge Skype Entreprise Server 2019 répertorié. 
  
9. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
     Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Pour publier les modifications de configuration du serveur Edge

1. Dans **le Générateur de topologie,** sélectionnez le nœud supérieur **Skype Entreprise Server**. 
    
2. Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant. 
    
3. Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.
    
    > [!NOTE]
    > Vous pouvez voir le message suivant : **Avertissement : la topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait activement utilisé pour la fédération. Vérifiez que l’enregistrement DNS SRV externe pointe vers le serveur Edge correct. Si vous souhaitez déployer plusieurs serveurs Edge de fédération pour qu’ils soient actifs simultanément (autrement dit, pas un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype Entreprise Server. Vérifiez que l’enregistrement SRV DNS** externe répertorie tous les serveurs Edge activés pour la fédération. Cet avertissement est attendu et peut être ignoré en toute sécurité. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Pour configurer Skype Entreprise Server serveur Edge 2019

1. Mettre tous les serveurs Edge Skype Entreprise Server 2019 en ligne. 
    
2. Mettez à jour les règles de routage du pare-feu externe ou les paramètres de l’équilibreur de charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la fédération (généralement le port 5061) vers le serveur Edge Skype Entreprise Server 2019, au lieu du serveur Edge hérité.
    
    > [!NOTE]
    > Si vous n’avez pas d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la fédération afin qu’il soit résolu vers le nouveau serveur Edge Skype Entreprise Server’accès. Pour y parvenir avec une perturbation minimale, réduisez la valeur de la TLL pour le FQDN edge d’accès Skype Entreprise Server externe de sorte que lorsque le DNS est mis à jour pour pointer vers le nouveau Skype Entreprise Server Le service Edge d’accès, la fédération et l’accès à distance seront mis à jour rapidement. 
  
3. Arrêtez le **serveur Edge Skype Entreprise Server’accès à** partir de chaque ordinateur serveur Edge. 
    
4. À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **outils d’administration.**
    
5. Dans la liste des services, recherchez **Skype Entreprise Server Edge d’accès.**
    
6. Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service. 
    
7. Définissez le type de démarrage sur **Désactivé**. 
    
8. Cliquez sur **OK** pour fermer la fenêtre **Propriétés**. 
    

