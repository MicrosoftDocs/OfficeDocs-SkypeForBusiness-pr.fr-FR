---
title: Suppression d’une configuration d’archivage
TOCTitle: Suppression d’une configuration d’archivage
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205167(v=OCS.15)
ms:contentKeyID: 49298450
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une configuration d’archivage

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez supprimer une configuration de site ou de pool. La configuration globale ne peut pas être supprimée. Si vous supprimez la configuration globale, elle est réinitialisée automatiquement aux valeurs par défaut. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment sur les options qui peuvent être spécifiées et la hiérarchie de configurations d’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

## Pour supprimer une configuration de site ou de pool pour l’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.

5.  Cliquez sur **Valider**.

## Suppression de paramètres de configuration d’archivage à l’aide d’applets de commande Lync Server Management Shell

La suppression des paramètres de configuration d’archivage peut également s’effectuer à l’aide de Windows PowerShell et de l’applet de commande Remove-CsArchivingConfiguration. Celle-ci peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

## Suppression d’une collection de paramètres de configuration d’archivage spécifiée

  - La commande suivante supprime les paramètres de configuration d’archivage appliqués au site Redmond.
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

## Suppression de tous les paramètres de configuration d’archivage appliqués à l’échelle du site

  - Cette commande supprime tous les paramètres de configuration d’archivage appliqués à l’échelle du service :
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

## Suppression de paramètres de configuration d’archivage en fonction d’une valeur de propriété spécifiée

  - Cette commande supprime tous les paramètres de configuration d’archivage là où l’archivage Exchange a été désactivé :
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingConfiguration).

## Voir aussi

#### Concepts

[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Autres ressources

[Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

