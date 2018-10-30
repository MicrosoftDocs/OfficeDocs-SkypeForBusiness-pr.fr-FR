---
title: Activer la qualité de l’expérience
TOCTitle: Activer la qualité de l’expérience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182583(v=OCS.15)
ms:contentKeyID: 49298837
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer la qualité de l’expérience

 

_**Dernière rubrique modifiée :** 2013-02-23_

La qualité de l’expérience (QoE) enregistre des données numériques qui indiquent la qualité du média, ainsi que les informations sur les participants, les noms des appareils, les pilotes, les adresses IP et les types de point de terminaison impliqués dans les appels et les sessions. Pour plus d’informations, voir [Planification de la surveillance dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md) dans la documentation de planification.

Procédez comme suit pour activer la QoE dans toute l’entreprise ou dans chacun de ses sites.

> [!NOTE]  
> Pour activer la qualité de l’expérience, vous devez commencer par configurer la surveillance et une base de données principale de surveillance. Pour plus d’informations, voir <a href="lync-server-2013-deploying-monitoring.md">Déploiement du serveur de surveillance dans Lync Server 2013</a>.

## Pour activer la qualité de l’expérience à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Données de qualité de l’expérience**.

4.  Dans la page **Données de qualité de l’expérience**, cliquez sur la collection appropriée dans le tableau, sur **Action**, puis sur **Activer QoE**.

## Activation de la qualité de l’expérience à l’aide d’applets de commande Windows PowerShell

Vous pouvez activer la qualité de l’expérience en utilisant Windows PowerShell et l’applet de commande **Set-CsQoEConfiguration**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer la qualité de l’expérience pour un emplacement

  - Pour activer la qualité de l’expérience, définissez le paramètre EnableQoE sur True ($True).
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

## Pour désactiver la qualité de l’expérience pour un emplacement

  - Pour désactiver la qualité de l’expérience, définissez le paramètre EnableQoE sur False ($False). Ceci ne désinstalle pas la surveillance, mais suspend la collecte et le stockage des données de qualité de l’expérience.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## Pour utiliser une commande pour activer la qualité de l’expérience dans plusieurs emplacements

  - Cette commande active la qualité de l’expérience pour tous les paramètres de configuration QoE actuellement utilisés dans votre organisation.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

Pour plus d’informations, voir [Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration).

## Voir aussi

#### Autres ressources

[Planification de la surveillance dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Déploiement du serveur de surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)

