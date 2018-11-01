---
title: "Spécif. de la rétention des données de l’enregistrement des détails des appels"
TOCtitle: "Spécif. de la rétention des données de l’enregistrement des détails des appels"
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182581(v=OCS.15)
ms:contentKeyID: 49298746
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Spécification de la rétention des données de l’enregistrement des détails des appels

 

_**Dernière rubrique modifiée :** 2013-02-23_

Par défaut, les données d’enregistrement des détails des appels sont vidées après un délai de 60 jours. Vous pouvez utiliser les paramètres de la page **Enregistrement des détails des appels** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez la fonctionnalité d’enregistrement des détails des appels, les données capturées avant l’enregistrement seront également vidées.

> [!NOTE]  
> Vous devez configurer l’enregistrement des détails des appels et la qualité de l’expérience (QoE) afin de conserver les données pendant le même nombre de jours. Chaque appel dans les rapports des détails des appels (disponibles à partir de la page web Rapports du serveur de surveillance) comprend des informations d’enregistrement des détails des appels et QoE. Si la durée de vidage pour les données d’enregistrement des détails des appels et de QoE est différente, certains appels peuvent inclure uniquement des données d’enregistrement des détails des appels et d’autres exclusivement des données QoE

Utilisez les procédures suivantes pour configurer les paramètres de vidage des données d’enregistrement des détails des appels.

## Pour spécifier la conservation des données d’enregistrement des détails des appels

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.

4.  Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.

5.  Pour activer le vidage, sélectionnez **Activer le vidage des enregistrements des détails des appels**.

6.  Dans **Conserver les enregistrements des détails des appels pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les enregistrements des détails des appels sont à conserver.

7.  Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.

8.  Cliquez sur **Valider**.

## Pour spécifier la conservation des enregistrements des détails des appels à l’aide des applets de commande de Lync Server Management Shell

Vous pouvez définir les paramètres de conservation des enregistrements des détails des appels en utilisant Windows PowerShell et l’applet de commande Set-CsCdrConfiguration. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour spécifier la conservation des enregistrements des détails des appels pour un emplacement particulier

  - Cette commande vide les enregistrements des détails des appels pour le site de Redmond, et configure ce site pour qu’il conserve les enregistrements des détails des appels et les données de signalement d’erreurs pendant 20 jours.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

## Pour spécifier la conservation des enregistrements des détails des appels pour plusieurs emplacements

  - Cette commande configure la conservation des enregistrements des détails des appels pour tous les paramètres de configuration des enregistrements des détails des appels actuellement appliqués dans l’organisation.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration).

## Voir aussi

#### Autres ressources

[Enregistrement des détails des appels (CDR) dans Lync Server 2013](lync-server-2013-call-detail-recording-cdr.md)

