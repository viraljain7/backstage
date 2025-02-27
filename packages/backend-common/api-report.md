## API Report File for "@backstage/backend-common"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="node" />
/// <reference types="webpack-env" />

import { AppConfig } from '@backstage/config';
import { AuthCallback } from 'isomorphic-git';
import { AuthService } from '@backstage/backend-plugin-api';
import { AwsCredentialsManager } from '@backstage/integration-aws-node';
import { AwsS3Integration } from '@backstage/integration';
import { AzureDevOpsCredentialsProvider } from '@backstage/integration';
import { AzureIntegration } from '@backstage/integration';
import { BackendFeature } from '@backstage/backend-plugin-api';
import { BitbucketCloudIntegration } from '@backstage/integration';
import { BitbucketIntegration } from '@backstage/integration';
import { BitbucketServerIntegration } from '@backstage/integration';
import { CacheService as CacheClient } from '@backstage/backend-plugin-api';
import { CacheServiceOptions as CacheClientOptions } from '@backstage/backend-plugin-api';
import { CacheServiceSetOptions as CacheClientSetOptions } from '@backstage/backend-plugin-api';
import { Config } from '@backstage/config';
import cors from 'cors';
import Docker from 'dockerode';
import { ErrorRequestHandler } from 'express';
import express from 'express';
import { GerritIntegration } from '@backstage/integration';
import { GiteaIntegration } from '@backstage/integration';
import { GithubCredentialsProvider } from '@backstage/integration';
import { GithubIntegration } from '@backstage/integration';
import { GitLabIntegration } from '@backstage/integration';
import { HostDiscovery as HostDiscovery_2 } from '@backstage/backend-app-api';
import { HttpAuthService } from '@backstage/backend-plugin-api';
import { IdentityService } from '@backstage/backend-plugin-api';
import { isChildPath } from '@backstage/cli-common';
import { Knex } from 'knex';
import knexFactory from 'knex';
import { KubeConfig } from '@kubernetes/client-node';
import { LifecycleService } from '@backstage/backend-plugin-api';
import { LoadConfigOptionsRemote } from '@backstage/config-loader';
import { Logger } from 'winston';
import { LoggerService } from '@backstage/backend-plugin-api';
import { MergeResult } from 'isomorphic-git';
import { PermissionsService } from '@backstage/backend-plugin-api';
import { DatabaseService as PluginDatabaseManager } from '@backstage/backend-plugin-api';
import { DiscoveryService as PluginEndpointDiscovery } from '@backstage/backend-plugin-api';
import { PluginMetadataService } from '@backstage/backend-plugin-api';
import { PushResult } from 'isomorphic-git';
import { Readable } from 'stream';
import { ReadCommitResult } from 'isomorphic-git';
import { ReadTreeOptions } from '@backstage/backend-plugin-api';
import { ReadTreeResponse } from '@backstage/backend-plugin-api';
import { ReadTreeResponseDirOptions } from '@backstage/backend-plugin-api';
import { ReadTreeResponseFile } from '@backstage/backend-plugin-api';
import { ReadUrlOptions } from '@backstage/backend-plugin-api';
import { ReadUrlResponse } from '@backstage/backend-plugin-api';
import { RequestHandler } from 'express';
import { RootConfigService } from '@backstage/backend-plugin-api';
import { Router } from 'express';
import { SchedulerService } from '@backstage/backend-plugin-api';
import { SearchOptions } from '@backstage/backend-plugin-api';
import { SearchResponse } from '@backstage/backend-plugin-api';
import { SearchResponseFile } from '@backstage/backend-plugin-api';
import { Server } from 'http';
import { ServiceRef } from '@backstage/backend-plugin-api';
import { TokenManagerService as TokenManager } from '@backstage/backend-plugin-api';
import { TransportStreamOptions } from 'winston-transport';
import { UrlReaderService as UrlReader } from '@backstage/backend-plugin-api';
import { V1PodTemplateSpec } from '@kubernetes/client-node';
import * as winston from 'winston';
import { Writable } from 'stream';

// @public
export type AuthCallbackOptions = {
  onAuth: AuthCallback;
  logger?: LoggerService;
};

// @public
export class AwsS3UrlReader implements UrlReader {
  constructor(
    credsManager: AwsCredentialsManager,
    integration: AwsS3Integration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export class AzureUrlReader implements UrlReader {
  constructor(
    integration: AzureIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
      credentialsProvider: AzureDevOpsCredentialsProvider;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(url: string, options?: SearchOptions): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export class BitbucketCloudUrlReader implements UrlReader {
  constructor(
    integration: BitbucketCloudIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(url: string, options?: SearchOptions): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export class BitbucketServerUrlReader implements UrlReader {
  constructor(
    integration: BitbucketServerIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(url: string, options?: SearchOptions): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public @deprecated
export class BitbucketUrlReader implements UrlReader {
  constructor(
    integration: BitbucketIntegration,
    logger: LoggerService,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(url: string, options?: SearchOptions): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

export { CacheClient };

export { CacheClientOptions };

export { CacheClientSetOptions };

// @public
export class CacheManager {
  forPlugin(pluginId: string): PluginCacheManager;
  static fromConfig(
    config: Config,
    options?: CacheManagerOptions,
  ): CacheManager;
}

// @public
export type CacheManagerOptions = {
  logger?: LoggerService;
  onError?: (err: Error) => void;
};

// @public (undocumented)
export function cacheToPluginCacheManager(
  cache: CacheClient,
): PluginCacheManager;

// @public
export const coloredFormat: winston.Logform.Format;

// @public
export interface ContainerRunner {
  runContainer(opts: RunContainerOptions): Promise<void>;
}

// @public
export function createDatabaseClient(
  dbConfig: Config,
  overrides?: Partial<Knex.Config>,
  deps?: {
    lifecycle: LifecycleService;
    pluginMetadata: PluginMetadataService;
  },
): knexFactory.Knex<any, any[]>;

// @public
export function createLegacyAuthAdapters<
  TOptions extends {
    auth?: AuthService;
    httpAuth?: HttpAuthService;
    identity?: IdentityService;
    tokenManager?: TokenManager;
    discovery: PluginEndpointDiscovery;
  },
  TAdapters = TOptions extends {
    auth?: AuthService;
  }
    ? TOptions extends {
        httpAuth?: HttpAuthService;
      }
      ? {
          auth: AuthService;
          httpAuth: HttpAuthService;
        }
      : {
          auth: AuthService;
        }
    : TOptions extends {
        httpAuth?: HttpAuthService;
      }
    ? {
        httpAuth: HttpAuthService;
      }
    : 'error: at least one of auth and/or httpAuth must be provided',
>(options: TOptions): TAdapters;

// @public
export function createRootLogger(
  options?: winston.LoggerOptions,
  env?: NodeJS.ProcessEnv,
): winston.Logger;

// @public
export function createServiceBuilder(_module: NodeModule): ServiceBuilder;

// @public
export function createStatusCheckRouter(options: {
  logger: LoggerService;
  path?: string;
  statusCheck?: StatusCheck;
}): Promise<express.Router>;

// @public
export class DatabaseManager implements LegacyRootDatabaseService {
  forPlugin(
    pluginId: string,
    deps?: {
      lifecycle: LifecycleService;
      pluginMetadata: PluginMetadataService;
    },
  ): PluginDatabaseManager;
  static fromConfig(
    config: Config,
    options?: DatabaseManagerOptions,
  ): DatabaseManager;
}

// @public
export type DatabaseManagerOptions = {
  migrations?: PluginDatabaseManager['migrations'];
  logger?: LoggerService;
};

// @public
export class DockerContainerRunner implements ContainerRunner {
  constructor(options: { dockerClient: Docker });
  // (undocumented)
  runContainer(options: RunContainerOptions): Promise<void>;
}

// @public
export function dropDatabase(
  dbConfig: Config,
  ...databases: Array<string>
): Promise<void>;

// @public
export function ensureDatabaseExists(
  dbConfig: Config,
  ...databases: Array<string>
): Promise<void>;

// @public
export function errorHandler(
  options?: ErrorHandlerOptions,
): ErrorRequestHandler;

// @public
export type ErrorHandlerOptions = {
  showStackTraces?: boolean;
  logger?: LoggerService;
  logClientErrors?: boolean;
};

// @public
export class FetchUrlReader implements UrlReader {
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export type FromReadableArrayOptions = Array<{
  data: Readable;
  path: string;
  lastModifiedAt?: Date;
}>;

// @public
export class GerritUrlReader implements UrlReader {
  constructor(
    integration: GerritIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
    workDir: string,
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export function getRootLogger(): winston.Logger;

// @public
export function getVoidLogger(): winston.Logger;

// @public
export class Git {
  // (undocumented)
  add(options: { dir: string; filepath: string }): Promise<void>;
  // (undocumented)
  addRemote(options: {
    dir: string;
    remote: string;
    url: string;
    force?: boolean;
  }): Promise<void>;
  // (undocumented)
  branch(options: { dir: string; ref: string }): Promise<void>;
  // (undocumented)
  checkout(options: { dir: string; ref: string }): Promise<void>;
  clone(options: {
    url: string;
    dir: string;
    ref?: string;
    depth?: number;
    noCheckout?: boolean;
  }): Promise<void>;
  // (undocumented)
  commit(options: {
    dir: string;
    message: string;
    author: {
      name: string;
      email: string;
    };
    committer: {
      name: string;
      email: string;
    };
  }): Promise<string>;
  currentBranch(options: {
    dir: string;
    fullName?: boolean;
  }): Promise<string | undefined>;
  // (undocumented)
  deleteRemote(options: { dir: string; remote: string }): Promise<void>;
  fetch(options: {
    dir: string;
    remote?: string;
    tags?: boolean;
  }): Promise<void>;
  // (undocumented)
  static fromAuth: (options: StaticAuthOptions | AuthCallbackOptions) => Git;
  // (undocumented)
  init(options: { dir: string; defaultBranch?: string }): Promise<void>;
  log(options: { dir: string; ref?: string }): Promise<ReadCommitResult[]>;
  merge(options: {
    dir: string;
    theirs: string;
    ours?: string;
    author: {
      name: string;
      email: string;
    };
    committer: {
      name: string;
      email: string;
    };
  }): Promise<MergeResult>;
  // (undocumented)
  push(options: {
    dir: string;
    remote: string;
    remoteRef?: string;
    force?: boolean;
  }): Promise<PushResult>;
  readCommit(options: { dir: string; sha: string }): Promise<ReadCommitResult>;
  remove(options: { dir: string; filepath: string }): Promise<void>;
  resolveRef(options: { dir: string; ref: string }): Promise<string>;
}

// @public
export class GiteaUrlReader implements UrlReader {
  constructor(
    integration: GiteaIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export class GithubUrlReader implements UrlReader {
  constructor(
    integration: GithubIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
      credentialsProvider: GithubCredentialsProvider;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(url: string, options?: SearchOptions): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export class GitlabUrlReader implements UrlReader {
  constructor(
    integration: GitLabIntegration,
    deps: {
      treeResponseFactory: ReadTreeResponseFactory;
    },
  );
  // (undocumented)
  static factory: ReaderFactory;
  // (undocumented)
  read(url: string): Promise<Buffer>;
  // (undocumented)
  readTree(url: string, options?: ReadTreeOptions): Promise<ReadTreeResponse>;
  // (undocumented)
  readUrl(url: string, options?: ReadUrlOptions): Promise<ReadUrlResponse>;
  // (undocumented)
  search(url: string, options?: SearchOptions): Promise<SearchResponse>;
  // (undocumented)
  toString(): string;
}

// @public
export const HostDiscovery: typeof HostDiscovery_2;

export { isChildPath };

// @public
export function isDatabaseConflictError(e: unknown): boolean;

// @public
export class KubernetesContainerRunner implements ContainerRunner {
  constructor(options: KubernetesContainerRunnerOptions);
  // (undocumented)
  runContainer(options: RunContainerOptions): Promise<void>;
}

// @public
export type KubernetesContainerRunnerMountBase = {
  volumeName: string;
  basePath: string;
};

// @public
export type KubernetesContainerRunnerOptions = {
  kubeConfig: KubeConfig;
  name: string;
  namespace?: string;
  mountBase?: KubernetesContainerRunnerMountBase;
  podTemplate?: V1PodTemplateSpec;
  timeoutMs?: number;
};

// @public (undocumented)
export type LegacyCreateRouter<TEnv> = (deps: TEnv) => Promise<RequestHandler>;

// @public
export const legacyPlugin: (
  name: string,
  createRouterImport: Promise<{
    default: LegacyCreateRouter<
      TransformedEnv<
        {
          cache: CacheClient;
          config: RootConfigService;
          database: PluginDatabaseManager;
          discovery: PluginEndpointDiscovery;
          logger: LoggerService;
          permissions: PermissionsService;
          scheduler: SchedulerService;
          tokenManager: TokenManager;
          reader: UrlReader;
          identity: IdentityService;
        },
        {
          logger: (log: LoggerService) => Logger;
          cache: (cache: CacheClient) => PluginCacheManager;
        }
      >
    >;
  }>,
) => BackendFeature;

// @public
export type LegacyRootDatabaseService = {
  forPlugin(pluginId: string): PluginDatabaseManager;
};

// @public
export function loadBackendConfig(options: {
  logger: LoggerService;
  remote?: LoadConfigOptionsRemote;
  additionalConfigs?: AppConfig[];
  argv: string[];
  watch?: boolean;
}): Promise<Config>;

// @public (undocumented)
export function loggerToWinstonLogger(
  logger: LoggerService,
  opts?: TransportStreamOptions,
): Logger;

// @public
export function makeLegacyPlugin<
  TEnv extends Record<string, unknown>,
  TEnvTransforms extends {
    [key in keyof TEnv]?: (dep: TEnv[key]) => unknown;
  },
>(
  envMapping: {
    [key in keyof TEnv]: ServiceRef<TEnv[key]>;
  },
  envTransforms: TEnvTransforms,
): (
  name: string,
  createRouterImport: Promise<{
    default: LegacyCreateRouter<TransformedEnv<TEnv, TEnvTransforms>>;
  }>,
) => BackendFeature;

// @public
export function notFoundHandler(): RequestHandler;

// @public (undocumented)
export interface PluginCacheManager {
  // (undocumented)
  getClient(options?: CacheClientOptions): CacheClient;
}

export { PluginDatabaseManager };

export { PluginEndpointDiscovery };

// @public
export type ReaderFactory = (options: {
  config: Config;
  logger: LoggerService;
  treeResponseFactory: ReadTreeResponseFactory;
}) => UrlReaderPredicateTuple[];

export { ReadTreeOptions };

export { ReadTreeResponse };

export { ReadTreeResponseDirOptions };

// @public
export interface ReadTreeResponseFactory {
  // (undocumented)
  fromReadableArray(
    options: FromReadableArrayOptions,
  ): Promise<ReadTreeResponse>;
  // (undocumented)
  fromTarArchive(
    options: ReadTreeResponseFactoryOptions & {
      stripFirstDirectory?: boolean;
    },
  ): Promise<ReadTreeResponse>;
  // (undocumented)
  fromZipArchive(
    options: ReadTreeResponseFactoryOptions,
  ): Promise<ReadTreeResponse>;
}

// @public
export type ReadTreeResponseFactoryOptions = {
  stream: Readable;
  subpath?: string;
  etag: string;
  filter?: (
    path: string,
    info?: {
      size: number;
    },
  ) => boolean;
};

export { ReadTreeResponseFile };

export { ReadUrlOptions };

export { ReadUrlResponse };

// @public
export class ReadUrlResponseFactory {
  static fromNodeJSReadable(
    oldStyleStream: NodeJS.ReadableStream,
    options?: ReadUrlResponseFactoryFromStreamOptions,
  ): Promise<ReadUrlResponse>;
  static fromReadable(
    stream: Readable,
    options?: ReadUrlResponseFactoryFromStreamOptions,
  ): Promise<ReadUrlResponse>;
}

// @public
export type ReadUrlResponseFactoryFromStreamOptions = {
  etag?: string;
  lastModifiedAt?: Date;
};

// @public
export function redactWinstonLogLine(
  info: winston.Logform.TransformableInfo,
): winston.Logform.TransformableInfo;

// @public
export function requestLoggingHandler(logger?: LoggerService): RequestHandler;

// @public
export type RequestLoggingHandlerFactory = (
  logger?: LoggerService,
) => RequestHandler;

// @public
export function resolvePackagePath(name: string, ...paths: string[]): string;

// @public
export function resolveSafeChildPath(base: string, path: string): string;

// @public
export type RunContainerOptions = {
  imageName: string;
  command?: string | string[];
  args: string[];
  logStream?: Writable;
  mountDirs?: Record<string, string>;
  workingDir?: string;
  envVars?: Record<string, string>;
  pullImage?: boolean;
  defaultUser?: boolean;
};

export { SearchOptions };

export { SearchResponse };

export { SearchResponseFile };

// @public
export class ServerTokenManager implements TokenManager {
  // (undocumented)
  authenticate(token: string): Promise<void>;
  // (undocumented)
  static fromConfig(
    config: Config,
    options: ServerTokenManagerOptions,
  ): ServerTokenManager;
  // (undocumented)
  getToken(): Promise<{
    token: string;
  }>;
  static noop(): TokenManager;
}

// @public
export interface ServerTokenManagerOptions {
  logger: LoggerService;
}

// @public
export type ServiceBuilder = {
  loadConfig(config: Config): ServiceBuilder;
  setPort(port: number): ServiceBuilder;
  setHost(host: string): ServiceBuilder;
  setLogger(logger: LoggerService): ServiceBuilder;
  enableCors(options: cors.CorsOptions): ServiceBuilder;
  setHttpsSettings(settings: {
    certificate:
      | {
          key: string;
          cert: string;
        }
      | {
          hostname: string;
        };
  }): ServiceBuilder;
  addRouter(root: string, router: Router | RequestHandler): ServiceBuilder;
  setRequestLoggingHandler(
    requestLoggingHandler: RequestLoggingHandlerFactory,
  ): ServiceBuilder;
  setErrorHandler(errorHandler: ErrorRequestHandler): ServiceBuilder;
  disableDefaultErrorHandler(): ServiceBuilder;
  start(): Promise<Server>;
};

// @public
export function setRootLogger(newLogger: winston.Logger): void;

// @public @deprecated
export const SingleHostDiscovery: typeof HostDiscovery_2;

// @public
export type StaticAuthOptions = {
  username?: string;
  password?: string;
  token?: string;
  logger?: LoggerService;
};

// @public
export type StatusCheck = () => Promise<any>;

// @public
export function statusCheckHandler(
  options?: StatusCheckHandlerOptions,
): Promise<RequestHandler>;

// @public
export interface StatusCheckHandlerOptions {
  statusCheck?: StatusCheck;
}

export { TokenManager };

export { UrlReader };

// @public
export type UrlReaderPredicateTuple = {
  predicate: (url: URL) => boolean;
  reader: UrlReader;
};

// @public
export class UrlReaders {
  static create(options: UrlReadersOptions): UrlReader;
  static default(options: UrlReadersOptions): UrlReader;
}

// @public
export type UrlReadersOptions = {
  config: Config;
  logger: LoggerService;
  factories?: ReaderFactory[];
};

// @public @deprecated
export function useHotCleanup(
  _module: NodeModule,
  cancelEffect: () => void,
): void;

// @public @deprecated
export function useHotMemoize<T>(_module: NodeModule, valueFactory: () => T): T;
```
