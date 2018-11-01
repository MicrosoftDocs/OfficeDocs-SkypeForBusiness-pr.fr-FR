---
title: "Install. d’un certif. sur un nœud observ. situé en dehors du réseau de périm."
TOCtitle: "Install. d’un certif. sur un nœud observ. situé en dehors du réseau de périm."
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49891419
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les agents System Center Operations Manager qui s’exécutent dans un réseau de périmètre (tel qu’un serveur Edge Lync Server), en dehors de l’entreprise (par exemple un nœud observateur de transaction synthétique externe), ou sur une délimitation d’approbation services de domaine Active Directory, peuvent exiger la configuration d’un serveur de passerelle System Center Operations Manager. Ce rôle serveur permet aux agents qui n’ont pas de relation d’approbation avec le serveur d’administration racine de déclencher des alertes. Pour plus d’informations, voir « Gestion des serveurs de passerelle dans Operations Manager 2007 » dans la bibliothèque TechNet System Center Operations Manager à l’adresse [http://go.microsoft.com/fwlink/?linkid=268703\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268703%26clcid=0x40c).

Si vous déployez un agent sur l’un de ces emplacements, vous devez également demander et configurer un certificat qui permet au nœud observateur d’envoyer des alertes à System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permet de demander et d’installer le type de certificat correct sur le nœud observateur. Pour plus d’informations et pour télécharger ces utilitaires, voir l’article de blog « Obtention de certificats pour des agents non joints au domaine avec l’Assistant Génération de certificat » à l’adresse [http://go.microsoft.com/fwlink/?linkid=267421\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267421%26clcid=0x40c).

