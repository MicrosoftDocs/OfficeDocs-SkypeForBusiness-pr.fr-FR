---
title: "Lync Server 2013 : Conf. du chiff. multimédia pour les fournisseurs publics"
TOCTitle: Configuration du chiffrement multimédia pour les fournisseurs publics
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205149(v=OCS.15)
ms:contentKeyID: 49298463
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du chiffrement multimédia pour les fournisseurs publics dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-12-12_

Pour plus d’informations sur les exigences de licence et savoir comment exécuter le processus d’approvisionnement, reportez-vous à « Guide de configuration de la connectivité PIC (Public IM Connectivity) pour Microsoft Lync Server, Office Communications Server et Live Communications Server » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=155970](http://go.microsoft.com/fwlink/p/?linkid=155970)

Si vous mettez en œuvre la fédération audio/vidéo (A/V) avec Windows Live Messenger, vous devez modifier deux paramètres : le niveau de chiffrement de Lync Server et la stratégie EnablePublicCloudAccess. Par défaut, le niveau de chiffrement est Requis. Vous devez définir ce paramètre sur Pris en charge. Si la stratégie EnablePublicCloudAccess a la valeur False, vous devez lui affecter la valeur **True** . Pour cela, utilisez Lync Server Management Shell.

> [!IMPORTANT]  
> Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. L’an prochain, la fédération avec Skype sera ajoutée à cette liste, permettant ainsi aux utilisateurs de Lync de joindre des millions de personnes par le biais de la messagerie instantanée et de la voix.

## Configurer la fédération pour Windows Live

1.  Démarrez Lync Server Management Shell sur le serveur frontal : cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Dans la ligne de commande, tapez les commandes suivantes :
    
    ```
    Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
    ```
    ```
    Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```
    
    > [!NOTE]  
    > Cette étape est obligatoire car Windows Live Messenger ne prend pas en charge le chiffrement de l’audio/vidéo. La commande affecte un paramètre de prise en charge du chiffrement à votre stratégie globale au lieu d’exiger le chiffrement des données audio/vidéo. Les clients qui prennent en charge le chiffrement, tels que Lync 2013, l’utiliseront toujours.
