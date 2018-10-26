---
title: "Créat. ou mod. d’une collection de param. de conf. de Lync Phone Edition"
TOCtitle: "Créat. ou mod. d’une collection de param. de conf. de Lync Phone Edition"
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49891384
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une collection de paramètres de configuration de Lync Phone Edition

 

_**Dernière rubrique modifiée :** 2013-02-23_

Lorsque vous installez Lync Server, vous obtenez une collection globale de paramètres Lync Phone Edition. Ces paramètres s’appliquent à tous les appareils qui exécutent Lync Phone Edition dans votre déploiement. Vous pouvez modifier ces paramètres à tout moment. Vous pouvez également configurer une nouvelle collection de paramètres qui s’applique aux appareils d’un site spécifique. Les paramètres du site prévalent sur les paramètres globaux.

Les paramètres de configuration comprennent le nom de la collection, l’étendue (globale ou site), le paramètre de sécurité SIP, le niveau de journalisation, le niveau de qualité de service de la voix (QoS), le paramètre de verrouillage du téléphone et les détails du verrouillage du téléphone, c’est-à-dire a) la longueur requise du code confidentiel de déverrouillage et b) le délai d’inactivité du téléphone avant son propre verrouillage.

## Pour créer une collection de paramètres de configuration Lync Phone Edition ou modifier les paramètres d’une collection existante

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, effectuez l’une des opérations suivantes :
    
      - Pour créer une collection de paramètres de configuration Lync Phone Edition, cliquez sur **Nouveau**, sélectionnez un site, cliquez sur **OK**, passez en revue les paramètres par défaut, puis apportez des modifications si vous le souhaitez.
    
      - Pour modifier l’un des paramètres d’une collection existante, cliquez sur la collection, cliquez sur le menu **Modifier**, cliquez sur **Afficher les détails**, puis apportez vos modifications.
        
        > [!TIP]  
        > Pour revenir à l’utilisation des paramètres par défaut de la collection globale, cliquez sur la collection globale, cliquez sur le menu <strong>Modifier</strong>, cliquez sur <strong>Supprimer</strong>, puis sur <strong>OK</strong>. Cela ne supprime pas la collection globale, mais rétablit simplement les paramètres à leurs valeurs par défaut.

5.  Cliquez sur **Valider**.

## Pour créer des paramètres de configuration Lync Phone Edition à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également créer des paramètres de configuration Lync Phone Edition (uniquement dans l’étendue du site) à l’aide de Lync Server Management Shell et de l’applet de commande **New-CsUCPhoneConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour créer des paramètres de configuration Lync Phone Edition qui utilisent les valeurs par défaut

  - Cette commande permet de créer un jeu de paramètres de configuration de téléphonie UC pour le site Redmond :
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Étant donné qu’aucun paramètre (autre que le paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.

## Pour modifier une seule valeur de propriété lors de la création de paramètres de configuration Lync Phone Edition

  - Pour créer des paramètres qui utilisent des valeurs de propriété différentes, il suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de téléphonie UC qui, par défaut, exige le verrouillage du téléphone, utilisez une commande comme celle-ci :
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

## Pour modifier plusieurs valeurs de propriété lors de la création de paramètres de configuration Lync Phone Edition

  - Il est possible de modifier plusieurs valeurs de propriété en incluant plusieurs paramètres. Par exemple, cette commande permet de mettre en application le verrouillage du téléphone et également de définir une longueur minimale de 8 chiffres pour le code confidentiel :
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

Pour plus d’informations, voir [New-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUCPhoneConfiguration).

## Voir aussi

#### Tâches

[Suppression d’une collection existante de paramètres de configuration Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configuration des paramètres de sécurité pour Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Application du verrouillage de téléphone](lync-server-2013-enforce-phone-locking.md)

