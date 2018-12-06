---
title: 'Lync Server 2013 : Configuration requise pour le plug-in Lync VDI'
TOCTitle: Configuration requise pour le plug-in Lync VDI
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205304(v=OCS.15)
ms:contentKeyID: 49299025
ms.date: 03/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour le plug-in Lync VDI dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2017-03-07_

Dans un environnement VDI (Virtual Desktop Infrastructure), les ordinateurs virtuels et l’ordinateur local de l’utilisateur doivent remplirent les conditions indiquées dans cette section.

> [!NOTE]  
> Consultez votre fournisseur de solution de virtualisation pour plus d’informations sur l’installation et le déploiement de l’environnement virtualisé. Pour plus d’informations sur le déploiement d’un environnement virtualisé basé sur Hyper-V et les services Bureau à distance, reportez-vous aux articles suivants de la bibliothèque Microsoft TechNet :<ul>
> <li><p>Hyper-V à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=247514" class="uri">http://go.microsoft.com/fwlink/p/?linkid=247514</a></p></li>
> <li><p>Services Bureau à distance dans Windows Server 2008 R2 à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=247513" class="uri">http://go.microsoft.com/fwlink/p/?linkid=247513</a></p></li></ul>


Les conditions suivantes s’appliquent aux ordinateurs virtuels exécutés sur l’ordinateur du centre de données :

  - Les ordinateurs virtuels doivent être configurés avec Windows 8, Windows 7 ou Windows Server 2008 R2 avec les derniers Service Packs.

Les conditions suivantes s’appliquent à l’utilisateur et à son ordinateur local :

  - L’utilisateur doit être hébergé sur Lync Server 2013.

  - L’ordinateur local doit exécuter Windows Embedded Standard 7 avec SP1, Windows 7 avec SP1 ou Windows 8.

  - Si vous utilisez les services Bureau à distance, le nombre de bits du plug-in Lync VDI (c’est-à-dire, si l’application est 32 bits ou 64 bits) doit correspondre au nombre de bits du système d’exploitation de l’ordinateur local. Il n’est pas utile que le nombre de bits du système d’exploitation sur l’ordinateur local et le système d’exploitation sur l’ordinateur virtuel correspondent. Si vous utilisez une autre solution ou plateforme de virtualisation, reportez-vous aux conseils de votre fournisseur de solution de virtualisation à propos des conditions relatives au nombre de bits.

  - L’ordinateur local doit exécuter la dernière version du client Bureau à distance. Installez les dernières mises à jour du client des services Bureau à distance de Microsoft ou le dernier logiciel du client Bureau à distance de votre fournisseur de solutions de virtualisation. Pour obtenir les dernières mises à jour des services Bureau à distance, reportez-vous à [http://go.microsoft.com/fwlink/p/?LinkId=268032](http://go.microsoft.com/fwlink/p/?linkid=268032).

  - Sur l’ordinateur local, les paramètres du client Bureau à distance doivent être configurés afin que le son soit lu sur l’ordinateur local et que l’enregistrement à distance soit désactivé. Pour configurer ces paramètres pour la connexion Bureau à distance dans Windows, reportez-vous à la section suivante intitulée « Pour configurer les paramètres de la connexion Bureau à distance ».

## Pour configurer les paramètres de la connexion Bureau à distance

Pour préparer la connexion Bureau à distance dans Windows pour le plug-in Lync VDI, procédez comme suit.

1.  Si l’ordinateur local exécute Windows 8, ignorez cette étape. S’il exécute Windows 7 avec SP1, installez la dernière version Windows 8 du client Services Bureau à distance, disponible à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=268032](http://go.microsoft.com/fwlink/p/?linkid=268032).

2.  Démarrez le client des services Bureau à distance en cliquant sur **Démarrer** , puis sur **Connexion Bureau à distance** .

3.  Cliquez sur **Options** .

4.  Cliquez sur l’onglet **Ressources locales** . Sous **Sortie audio de l’ordinateur distant** , cliquez sur **Paramètres** , puis procédez comme suit :
    
      - Sous **Lecture audio à distance** , sélectionnez **Lire sur cet ordinateur** .
    
      - Sous **Enregistrement audio à distance** , sélectionnez **Ne pas enregistrer** .
    
      - Cliquez sur **OK** .

5.  Cliquez sur l’onglet **Expérience** . Sous **Performance** , désactivez la case à cocher **Mise en cache permanente des bitmaps** .

6.  Cliquez sur l’onglet **Général** . Dans **Ordinateur** , tapez le nom de l’ordinateur virtuel, puis cliquez sur **Connecter** .

