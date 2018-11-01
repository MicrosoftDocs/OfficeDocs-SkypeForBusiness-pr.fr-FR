---
title: 'Lync Server 2013 : Installation des serveurs Edge'
TOCTitle: Installation des serveurs Edge
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398230(v=OCS.15)
ms:contentKeyID: 49296365
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation des serveurs Edge pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

L’installation de Lync Server 2013 sur les serveurs Edge s’effectue à l’aide de l’Assistant Déploiement de Lync Server. En exécutant l’Assistant Déploiement sur chaque serveur Edge, vous pouvez effectuer la plupart des tâches requises pour configurer le serveur Edge. Pour déployer Lync Server 2013 sur un serveur Edge, vous devez avoir déjà défini et publié la topologie du serveur Edge à l’aide du Générateur de topologie et avoir exporté la topologie sur un média auquel le serveur Edge peut accéder. Pour plus d’informations, reportez-vous à [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) et [Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Après avoir utilisé l’Assistant Déploiement pour installer chaque serveur Edge, installez et affectez les certificats requis, puis démarrez les services requis. Vous pouvez procéder à la configuration à l’aide des informations dans [Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) pour activer et configurer l’accès des utilisateurs externes et les informations dans [Vérification de votre déploiement Edge dans Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) pour valider la configuration ainsi que la connectivité des serveurs et des clients.

## Pour installer un serveur Edge

1.  Ouvrez une session sur l’ordinateur sur lequel vous souhaitez installer le serveur Edge en tant que membre du groupe Administrateurs local ou avec un compte disposant de droits et d’autorisations équivalents.

2.  Assurez-vous que le fichier de configuration de la topologie que vous avez créé à l’aide du Générateur de topologie et exporté et copié sur le média externe est disponible sur le serveur Edge. Par exemple, accédez au lecteur USB sur lequel vous avez copié le fichier de configuration de la topologie, ou vérifiez l’accès au partage réseau où vous avez copié le fichier.

3.  Démarrez l’Assistant Déploiement.
    
    > [!NOTE]  
    > Si vous obtenez un message vous indiquant que vous devez installer Microsoft Visual C++ Redistributable, cliquez sur <strong>Oui</strong>. Dans la boîte de dialogue suivante, acceptez l’<strong>emplacement d’installation</strong> par défaut ou cliquez sur <strong>Parcourir</strong> pour sélectionner un autre emplacement, puis cliquez sur <strong>Installer</strong>. Dans la boîte de dialogue suivante, activez la case à cocher <strong>J’accepte les termes du contrat de licence</strong>, puis cliquez sur <strong>OK</strong>.

4.  Dans l’Assistant Déploiement, cliquez sur **Installer ou mettre à jour le système Lync Server**.

5.  Une fois que l’Assistant a déterminé l’état du déploiement, pour **Étape 1. Installer le magasin de configurations local**, cliquez sur **Exécuter**, puis effectuez ce qui suit :
    
      - Dans la boîte de dialogue **Configurer le réplica local du magasin central de gestion**, cliquez sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**, accédez à l’emplacement du fichier de configuration de la topologie exporté, sélectionnez le fichier .zip, cliquez sur **Ouvrir**, puis sur **Suivant**.
    
      - L’Assistant Déploiement lit les informations de configuration du fichier de configuration et écrit le fichier de configuration XML sur l’ordinateur local.
    
      - Une fois que le processus **Exécution de commandes** est terminé, cliquez sur **Terminer**.

6.  Dans l’Assistant Déploiement, cliquez sur **Étape 2 : Installer ou supprimer des composants Lync Server** pour installer les composants Edge de Lync Server 2013 spécifiés dans le fichier de configuration XML stocké sur l’ordinateur local.

7.  Une fois l’installation terminée, utilisez les informations dans [Configuration des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) pour installer et affecter les certificats requis avant de démarrer les services.

