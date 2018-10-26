---
title: Activation du contournement de média réseau
TOCTitle: Activation du contournement de média réseau
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182552(v=OCS.15)
ms:contentKeyID: 49298128
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation du contournement de média réseau

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les paramètres de contournement de média s’appliquent globalement à un déploiement de Microsoft Lync Server 2013. Le contournement de média autorise les appels à contourner le serveur de médiation. Pour plus d’informations sur l’utilisation du contournement de média et quand l’utiliser, voir [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section Planification.

Vous pouvez activer et configurer le contournement de média à partir du Panneau de configuration Lync Server.

## Pour activer et configurer le contournement de média

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Globale**.

4.  Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contournement de média**.

7.  Sélectionnez l’une des options suivantes :
    
      - **Toujours ignorer**   Sélectionnez cette option pour tenter le contournement de média sur tous les appels. Cette option n’est pas disponible si le contrôle d’admission des appels est activé. S’il n’est pas activé, sélectionnez cette option dans les situations suivantes :
        
          - Il n’est pas nécessaire de contrôler la bande passante.
        
          - Il n’est pas nécessaire d’affiner la configuration pour déterminer à quel moment le contournement doit avoir lieu.
        
          - La connectivité entre passerelles et clients est complète.
    
      - **Utiliser la configuration des sites et des régions**   Si le contrôle d’admission des appels est activé, cette option est activée par défaut et n’est pas modifiable. Quand cette option est activée, la configuration réseau des sites et des régions sert à déterminer quand le contournement de média est possible. Si vous activez cette option, vous pouvez décider d’activer le contournement pour des sites non mappés. Activez la case à cocher **Activer le contournement pour les sites non mappés** uniquement si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez le contournement pour les sites non mappés, la configuration est rationalisée. Vous devez uniquement spécifier les sous-réseaux associés aux sites de succursale au lieu de devoir spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer la case à cocher **Activer le contournement pour les sites non mappés** si le contrôle d’admission des appels est activé.

8.  Cliquez sur **OK** pour enregistrer vos modifications.

## Voir aussi

#### Tâches

[Désactivation du contournement de média réseau](lync-server-2013-disabling-network-media-bypass.md)  

#### Concepts

[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Autres ressources

[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

