---
title: "Conf. par. gl. du cont. média ds LS 2013 pr ut. inf. rel. aux sites et rég."
TOCtitle: "Conf. par. gl. du cont. média ds LS 2013 pr ut. inf. rel. aux sites et rég."
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398150(v=OCS.15)
ms:contentKeyID: 49296208
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer les paramètres globaux du contournement de média dans Lync Server 2013 pour utiliser les informations relatives aux sites et aux régions

 

_**Dernière rubrique modifiée :** 2012-09-21_

> [!NOTE]  
> Cette rubrique suppose que vous avez déjà configuré le contournement de média pour des connexions de jonction depuis le serveur de médiation vers un homologue (une passerelle PSTN, un PBX IP ou un contrôleur SBC d’un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le contournement de média contourne toujours le serveur de médiation.<br />
Cette rubrique suppose également que vous avez défini tous les sites centraux et les sites de succursale dans le Générateur de topologie en veillant à ce qu’ils correspondent aux régions de réseau, sites réseau et sous-réseaux que vous avez configurés dans <a href="lync-server-2013-create-or-modify-a-network-region.md">Création ou modification d’une région réseau dans Lync Server 2013</a>, <a href="lync-server-2013-create-or-modify-a-network-site.md">Création ou modification d’un site réseau dans Lync Server 2013</a>, et <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Association d’un sous-réseau à un site réseau dans Lync Server 2013</a>. Si ce n’est pas le cas, le contournement de média échouera.

En plus d’activer le contournement de média pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres globaux. Si vous suivez la procédure indiquée dans cette rubrique pour configurer les paramètres globaux pour le contournement de média, les situations suivantes peuvent avoir un impact sur la configuration :

  - La connectivité entre les points de terminaison Lync Server et des homologues pour lesquels vous avez configuré le contournement de média sur la connexion de jonction *n’est pas* bonne.

  - Le contrôle d’admission des appels pour la gestion de la bande passante est activé.
    
    > [!NOTE]  
    > Pour plus d’informations sur les points importants concernant le contrôle d’admission des appels et le contournement de média, consultez la section Contrôle d’admission des appels des connexions PSTN de <a href="lync-server-2013-media-bypass-and-mediation-server.md">Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013</a> dans la documentation de planification.

Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de contournement de média lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure suivante pour modifier les informations relatives aux sites et aux régions destinées au contournement de média. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres du contournement de média.

Ou bien suivez ces étapes si vous souhaitez utiliser les informations relatives aux sites et aux régions pour appliquer le contournement de média sans activer le contrôle d’admission des appels. Dans ce cas, les liaisons à bande passante limitées devront quand même être représentées par le biais de stratégies intersites comme il est indiqué dans [Créer des stratégies inter-sites réseau](lync-server-2013-create-network-intersite-policies.md). Les contraintes réelles de bande passante ne sont pas aussi importantes dans ce cas, car le contrôle d’admission des appels n’a pas été activé. Ces liaisons servent alors à partitionner les sous-réseaux afin de déterminer ceux qui n’ont aucune limite de bande passante et qui peuvent par conséquent avoir recours au contournement de média. Notez que cela est également vrai lorsque le contrôle d’admission des appels et le contournement de média sont tous les deux activés.

De plus, pour que le contournement fonctionne correctement, un site défini dans le Générateur de topologie doit correspondre au même site défini lors de la configuration des régions et des sites réseau. Par exemple, si avez défini un site de succursale dans le Générateur de topologie avec une seule passerelle PSTN déployée, une stratégie Voix Entreprise qui achemine les appels PSTN des utilisateurs via la passerelle PSTN doit être configurée pour ce site.

## Pour configurer les informations relatives aux sites et aux régions pour le contournement de média

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Double-cliquez sur la configuration **Globale** dans le tableau.

4.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.

5.  Cliquez sur **Utiliser la configuration des sites et des régions**.

6.  Si nécessaire, activez la case à cocher **Activer le contournement pour les sites non mappés**.
    
    > [!NOTE]  
    > Activez uniquement cette case à cocher si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée. Vous devez uniquement spécifier les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé.

7.  Cliquez sur **Valider**.

Puis, ajoutez les sous-réseaux au site réseau comme il est indiqué dans [Associer des sous-réseaux à des sites réseau pour le contournement de média](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). (Les procédures pour associer des sous-réseaux à des sites réseau sont décrites dans [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Une fois que vous avez associé tous les sous-réseaux aux sites réseau, le déploiement du contournement de média est terminé.

> [!IMPORTANT]  
> Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour pouvoir poursuivre le déploiement du contournement de média. Pour plus d’informations, voir <a href="lync-server-2013-create-or-modify-a-network-region.md">Création ou modification d’une région réseau dans Lync Server 2013</a> et <a href="lync-server-2013-create-or-modify-a-network-site.md">Création ou modification d’un site réseau dans Lync Server 2013</a>.

## Voir aussi

#### Concepts

[Associer des sous-réseaux à des sites réseau pour le contournement de média](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)

