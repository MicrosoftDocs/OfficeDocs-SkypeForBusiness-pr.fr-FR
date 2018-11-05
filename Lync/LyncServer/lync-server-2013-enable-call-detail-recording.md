---
title: Actvier l’enregistrement des détails des appels
TOCTitle: Actvier l’enregistrement des détails des appels
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520980(v=OCS.15)
ms:contentKeyID: 49296931
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Actvier l’enregistrement des détails des appels

 

_**Dernière rubrique modifiée :** 2013-02-23_

La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.

Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.

> [!NOTE]  
> Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance. Pour plus d’informations, voir <a href="lync-server-2013-deploying-monitoring.md">Déploiement du serveur de surveillance dans Lync Server 2013</a>.

## Pour activer l’enregistrement des détails des appels à partir du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4.  Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.
    
    > [!NOTE]  
    > Cette fonctionnalité est activée par défaut.

## Pour activer l’enregistrement des détails des appels à l’aide des applets de commande Lync Server Management Shell

Vous pouvez aussi activer l’enregistrement des détails des appels à l’aide de Windows PowerShell et de l’applet de commande **Set-CsCdrConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer l’enregistrement des détails des appels pour un seul site

  - Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

## Pour désactiver l’enregistrement des détails des appels pour un seul site

  - Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False). Ce paramétrage n’a pas pour effet de désinstaller la surveillance ; il interrompt la collecte et le stockage des données d’enregistrement des détails des appels.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande

  - Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration).

## Voir aussi

#### Autres ressources

[Planification de la surveillance dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Déploiement du serveur de surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)

