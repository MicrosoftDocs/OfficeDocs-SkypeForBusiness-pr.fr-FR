---
title: "Suppr. d’une collection existante de par. de configuration Lync Phone Edition"
TOCtitle: "Suppr. d’une collection existante de par. de configuration Lync Phone Edition"
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49891252
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une collection existante de paramètres de configuration Lync Phone Edition

 

_**Dernière rubrique modifiée :** 2013-02-23_

Si vous ne souhaitez plus utiliser une collection de paramètres pour les périphériques qui exécutent Lync Phone Edition, supprimez-la. Si vous supprimez la collection de paramètres d’un site, les paramètres globaux s’appliqueront aux téléphones de ce site. Vous ne pouvez pas supprimer la collection globale.

> [!NOTE]  
> Au lieu de supprimer une collection, vous pouvez simplement modifier certains des paramètres. Pour en savoir plus à ce sujet, voir <a href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Création ou modification d’une collection de paramètres de configuration de Lync Phone Edition</a>.

## Pour supprimer une collection de paramètres de configuration Lync Phone Edition

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, cliquez sur la collection à supprimer, sur le menu **Edition**, puis sur **Supprimer**.
    
    > [!NOTE]  
    > Si vous supprimez la collection globale, les paramètres par défaut sont simplement rétablis. La collection ne disparaît pas.

5.  Dans la boîte de dialogue de confirmation, cliquez sur **OK**.

## Pour supprimer les paramètres de configuration Lync Phone Edition à l’aide des applets de commande Lync Server Management Shell

Vous pouvez supprimer les paramètres de configuration de Lync Phone Edition en utilisant Windows PowerShell et l’applet de commande **Remove-CsUCConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une collection spécifique de paramètres de configuration Lync Phone Edition

  - Cette commande permet de supprimer les paramètres de configuration du téléphone pour messagerie unifiée appliqués au site Redmond :
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

## Pour supprimer tous les paramètres de configuration Lync Phone Edition appliqués à l’étendue Site

  - Cette commande permet de supprimer tous les paramètres de configuration du téléphone pour messagerie unifiée appliqués à l’étendue Service :
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

## Pour supprimer tous les paramètres de configuration Lync Phone Edition dans lesquels le verrouillage du téléphone est désactivé

  - Cette commande permet de supprimer les collections de paramètres de configuration du téléphone pour messagerie unifiée dans lesquels le verrouillage du téléphone a été désactivé :
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

Pour plus d’informations, voir [Remove-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUCPhoneConfiguration).

