---
title: Déploiement du serveur Edge pilote
TOCTitle: Déploiement du serveur Edge pilote
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204682(v=OCS.15)
ms:contentKeyID: 49296299
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement du serveur Edge pilote

 

_**Dernière rubrique modifiée :** 2012-10-19_

Cette rubrique met en avant les paramètres de configuration dont vous devez avoir connaissance avant de déployer votre serveur EdgeLync Server 2013. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote Edge. Pour les étapes détaillées, reportez-vous à [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement ; celle-ci décrit le processus de déploiement et donne des informations de configuration pour l’accès des utilisateurs externes.

À mesure que vous parcourez l’Assistant **Définir un nouveau pool Edge** , examinez les principaux paramètres de configuration mentionnés aux étapes suivantes. Notez que seules quelques pages de l’Assistant **Définir un nouveau pool Edge** sont illustrées.

**Pour définir un pool Edge**

1.  Ouvrez la topologie du premier pool à l’aide du générateur de topologie.

2.  Accédez au nœud Lync Server 2013. Cliquez avec le bouton droit sur **Pools Edge** , puis cliquez sur **Nouveau pool de serveurs Edge** .
    
    ![Boîte de dialogue Définir le nouveau pool Edge](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue Définir le nouveau pool Edge")

3.  Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur** .
    
    ![Boîte de dialogue Définir le nom de domaine complet du pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Boîte de dialogue Définir le nom de domaine complet du pool Edge")

4.  Dans la page **Sélectionner les fonctionnalités** , n’activez pas la fédération ou la fédération XMPP. La fédération et la fédération XMPP sont actuellement routées par le biais du serveur EdgeOffice Communications Server 2007 R2 hérité. Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")

5.  Ensuite, continuez à remplir les pages suivantes de l’Assistant : **Sélectionner les options IP** , **Noms de domaine complets externes** , **Définir l’adresse IP interne** et **Définir l’adresse IP externe** .

6.  Dans la page **Définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs EdgeLync Server 2013.
    
    ![Boîte de dialogue Définir nouveau pool Edge, liste Pool du tronçon suivant](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Boîte de dialogue Définir nouveau pool Edge, liste Pool du tronçon suivant")

7.  Dans la page **Pools frontaux associés** , n’associez pas de pool à ce pool de serveurs Edge à ce stade. Le trafic multimédia externe est actuellement acheminé par le biais du serveur EdgeOffice Communications Server 2007 R2 hérité. Ce paramètre sera configuré lors d’une phase ultérieure de la migration.
    
    ![Boîte de dialogue Définir le nouveau pool Edge](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Boîte de dialogue Définir le nouveau pool Edge")

8.  Cliquez sur **Terminer** , puis sur **Publier** pour publier la topologie.

9.  Suivez les étapes décrites dans [Installation des serveurs Edge pour Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.

Il est essentiel de bien respecter les consignes fournies dans la rubrique [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) de la documentation de déploiement. Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.

Vous devez maintenant avoir un déploiement de serveur Edge Office Communications Server 2007 R2 hérité, indiqué par la présence de BackCompatSite, ainsi qu’un déploiement de serveur Edge Lync Server 2013. La fédération est configurée de façon à utiliser le directeur Office Communications Server 2007 R2. Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.

![Générateur de topologie montrant un serveur Edge OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Générateur de topologie montrant un serveur Edge OCS")

