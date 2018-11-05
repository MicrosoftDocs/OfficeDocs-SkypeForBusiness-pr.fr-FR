---
title: "Conf. le contourn. de média ds LS 2013 pr tjs contourner le serv. de médiation"
TOCtitle: "Conf. le contourn. de média ds LS 2013 pr tjs contourner le serv. de médiation"
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425846(v=OCS.15)
ms:contentKeyID: 49296857
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer le contournement de média dans Lync Server 2013 pour toujours contourner le serveur de médiation

 

_**Dernière rubrique modifiée :** 2013-02-25_

> [!NOTE]  
> Cette rubrique suppose que vous avez déjà configuré le contournement de média pour des connexions de jonction vers un homologue (une passerelle PSTN, un PBX IP ou un contrôleur SBC chez un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le contournement de média contourne toujours le serveur de médiation.<br />
Vous ne pouvez pas configurer le contournement de média pour qu’il contourne toujours le serveur de médiation alors que le contrôle d’admission des appels est activé. Ces paramètres étant incompatibles, ils s’excluent mutuellement dans l’interface utilisateur du Panneau de configuration Lync Server.

Outre l’activation du contournement de média pour des connexions de jonction individuelles associées à un homologue vers le serveur de médiation, vous devez également configurer les paramètres globaux du contournement de média. Si vous suivez la procédure indiquée dans cette rubrique pour configurer les paramètres globaux du contournement de média, vous êtes supposé disposer d’une bonne connectivité entre les points de terminaison Lync et tout homologue pour lequel vous avez configuré le contournement de média sur la connexion de jonction.

Si la connectivité est médiocre entre d’un côté les points de terminaison Lync Server et tous les homologues, et de l’autre le serveur de médiation dont les connexions de jonction sont activées pour le contournement de média, vous devez configurer les paramètres de contournement de média globaux pour utiliser les informations relatives aux sites et aux régions lorsque vous mettez en œuvre le contournement de média. Cela permet de déterminer plus précisément le moment auquel le média contourne le serveur de médiation. Pour ce faire, appliquez plutôt la procédure indiquée dans les rubriques [Configurer les paramètres globaux du contournement de média dans Lync Server 2013 pour utiliser les informations relatives aux sites et aux régions](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) et [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

## Pour activer le contournement de média au niveau global pour qu’il contourne toujours le serveur de médiation

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Double-cliquez sur la configuration **Globale** dans la liste.

4.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.

5.  Cliquez sur **Toujours ignorer**.

6.  Cliquez sur **Valider**.

## Voir aussi

#### Concepts

[Configuration de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  

#### Autres ressources

[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

