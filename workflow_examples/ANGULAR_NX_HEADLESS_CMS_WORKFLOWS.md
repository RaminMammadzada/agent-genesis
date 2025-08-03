# Angular NX Monorepo with Headless CMS Integration Workflow

## Overview

Comprehensive workflow for building enterprise-scale Angular applications using NX monorepo architecture with headless CMS backend integration. Focuses on Drupal/PHP-based headless CMS with Angular frontend ecosystem.

---

## 🏗️ **Enterprise Angular NX + Headless CMS Architecture**

### **Project Scope: Multi-Application Angular Ecosystem with Drupal Backend**

#### **Phase 1: Monorepo Foundation & Architecture (Weeks 1-3)**

##### **Agent Team Formation (20-30 agents)**

```bash
@genesis-meta-coordinator Assemble enterprise Angular NX + CMS team:

Architecture Council (5 agents):
- @agent-swarm-architect: Overall system architecture design
- @technology-stack-specialist: Technology selection and integration
- @agent-ecosystem-designer: Multi-team coordination strategy
- @evolution-strategy-planner: Long-term scalability planning
- @agent-performance-monitor: Performance oversight

Backend Specialists (6 agents):
- Drupal Headless Architect
- PHP/Symfony API Specialist
- Database Optimization Engineer
- GraphQL/REST API Designer
- Content Workflow Specialist
- Security & Authentication Expert

Frontend Specialists (8 agents):
- Angular Architecture Specialist
- NX Workspace Engineer
- NgRx State Management Expert
- Angular Material/CDK Specialist
- Performance Optimization Engineer
- Testing Strategy Coordinator
- Component Library Architect
- Micro-Frontend Integration Specialist

DevOps & Integration (6 agents):
- CI/CD Pipeline Engineer
- Container Orchestration Specialist
- Content Deployment Coordinator
- Monitoring & Analytics Engineer
- Security Compliance Officer
- Documentation & Knowledge Management
```

##### **NX Workspace Architecture Design**

```bash
@agent-swarm-architect Design comprehensive NX monorepo architecture:

Workspace Structure:
nx-workspace/
├── apps/                           # Applications
│   ├── admin-portal/              # CMS administration
│   ├── customer-portal/           # Customer-facing app
│   ├── public-website/            # Marketing website
│   ├── mobile-app/                # Ionic mobile app
│   ├── cms-preview/               # Content preview app
│   └── analytics-dashboard/       # Analytics app
├── libs/                          # Shared libraries
│   ├── shared/                    # Cross-application shared code
│   │   ├── ui/                   # Design system & components
│   │   ├── data-access/          # API services & state
│   │   ├── utils/                # Utility functions
│   │   ├── types/                # TypeScript interfaces
│   │   ├── auth/                 # Authentication logic
│   │   └── config/               # Configuration management
│   ├── cms/                      # CMS-specific libraries
│   │   ├── content-management/   # Content operations
│   │   ├── media-handling/       # Media management
│   │   ├── workflow/             # Content workflows
│   │   ├── preview/              # Content preview
│   │   └── analytics/            # Content analytics
│   ├── domain/                   # Domain-specific libraries
│   │   ├── user-management/      # User operations
│   │   ├── product-catalog/      # Product management
│   │   ├── order-processing/     # Order workflows
│   │   └── notification/         # Notification system
│   └── features/                 # Feature libraries
│       ├── dashboard/            # Dashboard components
│       ├── search/               # Search functionality
│       ├── reporting/            # Reporting features
│       └── settings/             # Settings management
├── tools/                        # Custom tools and scripts
│   ├── generators/               # NX code generators
│   ├── executors/                # Custom executors
│   └── migrations/               # Migration scripts
└── docs/                         # Documentation
    ├── architecture/             # Architecture docs
    ├── guidelines/               # Development guidelines
    └── api/                      # API documentation

NX Configuration Benefits:
- Dependency graph visualization and management
- Affected project detection for optimal CI/CD
- Code sharing and consistency across applications
- Automated testing and linting strategies
- Build optimization with computation caching
```

##### **Technology Stack Selection**

```bash
@technology-stack-specialist Select optimized tech stack for Angular NX + Headless CMS:

Backend Stack:
CMS & API:
- Drupal 10.x with JSON:API and GraphQL modules
- PHP 8.2+ with OPcache optimization
- Symfony components for custom API logic
- MySQL 8.0 / PostgreSQL 15 for data storage
- Redis for caching and session management
- Elasticsearch for advanced search capabilities

API Architecture:
- GraphQL for flexible data fetching
- JSON:API for standardized REST endpoints
- WebSocket connections for real-time updates
- JWT authentication with refresh tokens
- OAuth 2.0 for third-party integrations

Frontend Stack:
Angular Ecosystem:
- Angular 16+ with standalone components
- NX 16+ for monorepo management
- NgRx 16+ for state management
- Angular Material 16+ for UI components
- Angular CDK for advanced UI patterns
- RxJS for reactive programming

Development Tools:
- TypeScript 5+ with strict mode
- ESLint + Prettier for code quality
- Jest for unit testing
- Cypress for E2E testing
- Storybook for component documentation
- Angular Universal for SSR

Build & Deployment:
- NX Cloud for distributed computation
- Docker for containerization
- Kubernetes for orchestration
- GitHub Actions / GitLab CI for pipelines
- Terraform for infrastructure as code
```

#### **Phase 2: Headless CMS Backend Development (Weeks 4-8)**

##### **Drupal Headless Architecture Setup**

```bash
@drupal-specialist Setup comprehensive Drupal headless architecture:

Drupal Configuration:
# Install Drupal with headless profile
composer create-project drupal/recommended-project:^10 cms-backend
cd cms-backend

# Essential headless modules
composer require drupal/jsonapi_extras
composer require drupal/graphql
composer require drupal/cors
composer require drupal/consumers
composer require drupal/simple_oauth
composer require drupal/subrequests
composer require drupal/decoupled_router

# Performance and caching modules
composer require drupal/redis
composer require drupal/memcache
composer require drupal/purge
composer require drupal/varnish_purge

Content Architecture:
Content Types:
- Articles (with rich media support)
- Pages (for static content)
- Products (e-commerce integration)
- Events (with calendar integration)
- Landing Pages (with layout builder)
- Media Gallery (advanced media handling)

Custom Fields:
- Rich text with media embedding
- Image galleries with responsive variants
- Video embedding with thumbnails
- File attachments with metadata
- Geolocation data
- SEO metadata fields
- Social sharing metadata
```

##### **Advanced API Development**

```bash
@api-designer Create sophisticated API layer:

GraphQL Schema Design:
# Custom GraphQL schema
type Article {
  id: ID!
  title: String!
  body: String
  author: User!
  publishedAt: DateTime
  updatedAt: DateTime
  status: PublishStatus!
  tags: [Tag!]!
  featuredImage: MediaImage
  gallery: [MediaImage!]
  seoMetadata: SeoData
  translations: [Translation!]
}

type Query {
  articles(
    filter: ArticleFilter
    sort: ArticleSort
    pagination: PaginationInput
  ): ArticleConnection!

  article(id: ID!): Article

  searchContent(
    query: String!
    type: ContentType
    filters: SearchFilters
  ): SearchResults!
}

Custom API Controllers:
<?php
namespace Drupal\custom_api\Controller;

use Drupal\Core\Controller\ControllerBase;
use Symfony\Component\HttpFoundation\JsonResponse;
use Symfony\Component\HttpFoundation\Request;

class ContentApiController extends ControllerBase {

  /**
   * Advanced content retrieval with filtering and sorting
   */
  public function getContent(Request $request, $content_type) {
    $query_params = $request->query->all();

    $query = \Drupal::entityQuery('node')
      ->condition('type', $content_type)
      ->condition('status', 1);

    // Apply filters
    if (!empty($query_params['filters'])) {
      foreach ($query_params['filters'] as $field => $value) {
        $query->condition($field, $value);
      }
    }

    // Apply sorting
    if (!empty($query_params['sort'])) {
      $sort_field = $query_params['sort']['field'] ?? 'created';
      $sort_direction = $query_params['sort']['direction'] ?? 'DESC';
      $query->sort($sort_field, $sort_direction);
    }

    // Apply pagination
    $page = $query_params['page'] ?? 0;
    $limit = $query_params['limit'] ?? 20;
    $query->range($page * $limit, $limit);

    $entity_ids = $query->execute();
    $entities = \Drupal::entityTypeManager()
      ->getStorage('node')
      ->loadMultiple($entity_ids);

    $serializer = \Drupal::service('serializer');
    $data = [];

    foreach ($entities as $entity) {
      $normalized = $serializer->normalize($entity, 'json', [
        'include_computed_fields' => TRUE,
        'include_relationships' => TRUE,
      ]);
      $data[] = $normalized;
    }

    return new JsonResponse([
      'data' => $data,
      'meta' => [
        'page' => $page,
        'limit' => $limit,
        'total' => count($entity_ids),
      ],
    ]);
  }

  /**
   * Real-time content preview
   */
  public function previewContent(Request $request) {
    $content = json_decode($request->getContent(), TRUE);

    // Create temporary entity for preview
    $entity = \Drupal::entityTypeManager()
      ->getStorage('node')
      ->create($content);

    $view_builder = \Drupal::entityTypeManager()
      ->getViewBuilder('node');

    $preview = $view_builder->view($entity, 'preview');
    $rendered = \Drupal::service('renderer')->render($preview);

    return new JsonResponse([
      'preview' => (string) $rendered,
      'metadata' => [
        'timestamp' => time(),
        'cache_tags' => $preview['#cache']['tags'] ?? [],
      ],
    ]);
  }
}

WebSocket Integration:
<?php
namespace Drupal\custom_api\WebSocket;

use Ratchet\MessageComponentInterface;
use Ratchet\ConnectionInterface;

class ContentUpdateServer implements MessageComponentInterface {
  protected $clients;

  public function __construct() {
    $this->clients = new \SplObjectStorage;
  }

  public function onOpen(ConnectionInterface $conn) {
    $this->clients->attach($conn);
    echo "New connection! ({$conn->resourceId})\n";
  }

  public function onMessage(ConnectionInterface $from, $msg) {
    $data = json_decode($msg, true);

    // Broadcast content updates to subscribed clients
    if ($data['type'] === 'content_update') {
      foreach ($this->clients as $client) {
        if ($from !== $client) {
          $client->send(json_encode([
            'type' => 'content_updated',
            'content_id' => $data['content_id'],
            'action' => $data['action'],
            'timestamp' => time(),
          ]));
        }
      }
    }
  }
}
```

#### **Phase 3: Angular Applications Development (Weeks 9-16)**

##### **Shared Libraries Development**

```bash
@angular-architect Create comprehensive shared library ecosystem:

Core Shared UI Library:
libs/shared/ui/
├── src/
│   ├── lib/
│   │   ├── components/           # Reusable components
│   │   │   ├── layout/          # Layout components
│   │   │   ├── navigation/       # Navigation components
│   │   │   ├── forms/           # Form components
│   │   │   ├── data-display/    # Data display components
│   │   │   └── feedback/        # Feedback components
│   │   ├── directives/          # Custom directives
│   │   ├── pipes/               # Custom pipes
│   │   ├── services/            # UI-related services
│   │   └── tokens/              # Injection tokens
│   ├── styles/                  # Global styles
│   │   ├── _variables.scss      # SCSS variables
│   │   ├── _mixins.scss         # SCSS mixins
│   │   └── _themes.scss         # Theme definitions
│   └── assets/                  # Static assets
└── ng-package.json

// Example: Advanced form component
@Component({
  selector: 'app-dynamic-form',
  template: `
    <form [formGroup]="form" (ngSubmit)="onSubmit()">
      <ng-container *ngFor="let field of formConfig.fields">
        <div [ngSwitch]="field.type" class="form-field">

          <!-- Text input -->
          <mat-form-field *ngSwitchCase="'text'">
            <mat-label>{{ field.label }}</mat-label>
            <input matInput [formControlName]="field.name" [placeholder]="field.placeholder">
            <mat-error *ngIf="getFieldError(field.name)">
              {{ getFieldError(field.name) }}
            </mat-error>
          </mat-form-field>

          <!-- Rich text editor -->
          <div *ngSwitchCase="'richtext'" class="rich-text-field">
            <label>{{ field.label }}</label>
            <editor
              [formControlName]="field.name"
              [init]="editorConfig"
              (onInit)="onEditorInit($event)">
            </editor>
          </div>

          <!-- Media upload -->
          <app-media-upload
            *ngSwitchCase="'media'"
            [formControlName]="field.name"
            [accept]="field.accept"
            [multiple]="field.multiple">
          </app-media-upload>

        </div>
      </ng-container>

      <div class="form-actions">
        <button
          mat-raised-button
          color="primary"
          type="submit"
          [disabled]="form.invalid || isSubmitting">
          {{ isSubmitting ? 'Saving...' : 'Save' }}
        </button>
      </div>
    </form>
  `,
  changeDetection: ChangeDetectionStrategy.OnPush,
})
export class DynamicFormComponent implements OnInit {
  @Input() formConfig!: FormConfig;
  @Input() initialData?: any;
  @Output() formSubmit = new EventEmitter<any>();

  form!: FormGroup;
  isSubmitting = false;

  constructor(
    private fb: FormBuilder,
    private cdr: ChangeDetectorRef
  ) {}

  ngOnInit() {
    this.buildForm();
  }

  private buildForm() {
    const controls: { [key: string]: FormControl } = {};

    this.formConfig.fields.forEach(field => {
      const validators = this.buildValidators(field.validation);
      const initialValue = this.initialData?.[field.name] || field.defaultValue || '';

      controls[field.name] = new FormControl(initialValue, validators);
    });

    this.form = this.fb.group(controls);
  }

  private buildValidators(validation?: ValidationConfig): ValidatorFn[] {
    const validators: ValidatorFn[] = [];

    if (validation?.required) {
      validators.push(Validators.required);
    }

    if (validation?.minLength) {
      validators.push(Validators.minLength(validation.minLength));
    }

    if (validation?.maxLength) {
      validators.push(Validators.maxLength(validation.maxLength));
    }

    if (validation?.pattern) {
      validators.push(Validators.pattern(validation.pattern));
    }

    return validators;
  }
}

Data Access Library:
libs/shared/data-access/
├── src/
│   ├── lib/
│   │   ├── services/             # API services
│   │   │   ├── content.service.ts
│   │   │   ├── auth.service.ts
│   │   │   ├── media.service.ts
│   │   │   └── search.service.ts
│   │   ├── interceptors/         # HTTP interceptors
│   │   │   ├── auth.interceptor.ts
│   │   │   ├── error.interceptor.ts
│   │   │   └── cache.interceptor.ts
│   │   ├── guards/               # Route guards
│   │   │   ├── auth.guard.ts
│   │   │   └── role.guard.ts
│   │   ├── models/               # Data models
│   │   │   ├── content.model.ts
│   │   │   ├── user.model.ts
│   │   │   └── api-response.model.ts
│   │   └── state/                # NgRx state management
│   │       ├── content/          # Content state
│   │       ├── auth/             # Authentication state
│   │       └── ui/               # UI state
│   └── index.ts

// Advanced content service with caching and error handling
@Injectable({ providedIn: 'root' })
export class ContentService {
  private readonly apiUrl = environment.apiUrl;
  private cache = new Map<string, { data: any; timestamp: number }>();
  private readonly cacheTimeout = 5 * 60 * 1000; // 5 minutes

  constructor(
    private http: HttpClient,
    private errorHandler: ErrorHandlerService,
    private logger: LoggerService
  ) {}

  getContent<T>(
    contentType: string,
    options: ContentQueryOptions = {}
  ): Observable<PaginatedResponse<T>> {
    const cacheKey = this.buildCacheKey(contentType, options);
    const cachedData = this.getCachedData(cacheKey);

    if (cachedData) {
      return of(cachedData);
    }

    const params = this.buildQueryParams(options);

    return this.http.get<PaginatedResponse<T>>(
      `${this.apiUrl}/content/${contentType}`,
      { params }
    ).pipe(
      tap(response => this.setCachedData(cacheKey, response)),
      catchError(error => this.handleError(error)),
      finalize(() => this.logger.debug(`Fetched ${contentType} content`))
    );
  }

  getContentById<T>(contentType: string, id: string): Observable<T> {
    return this.http.get<T>(`${this.apiUrl}/content/${contentType}/${id}`)
      .pipe(
        catchError(error => this.handleError(error))
      );
  }

  createContent<T>(contentType: string, data: Partial<T>): Observable<T> {
    return this.http.post<T>(`${this.apiUrl}/content/${contentType}`, data)
      .pipe(
        tap(() => this.invalidateCache(contentType)),
        catchError(error => this.handleError(error))
      );
  }

  updateContent<T>(
    contentType: string,
    id: string,
    data: Partial<T>
  ): Observable<T> {
    return this.http.patch<T>(
      `${this.apiUrl}/content/${contentType}/${id}`,
      data
    ).pipe(
      tap(() => this.invalidateCache(contentType)),
      catchError(error => this.handleError(error))
    );
  }

  private buildQueryParams(options: ContentQueryOptions): HttpParams {
    let params = new HttpParams();

    if (options.filters) {
      Object.entries(options.filters).forEach(([key, value]) => {
        params = params.set(`filter[${key}]`, value.toString());
      });
    }

    if (options.sort) {
      params = params.set('sort', `${options.sort.field}:${options.sort.direction}`);
    }

    if (options.include) {
      params = params.set('include', options.include.join(','));
    }

    if (options.page) {
      params = params.set('page', options.page.toString());
    }

    if (options.limit) {
      params = params.set('limit', options.limit.toString());
    }

    return params;
  }

  private handleError(error: any): Observable<never> {
    this.logger.error('Content service error:', error);
    return this.errorHandler.handleError(error);
  }
}
```

##### **NgRx State Management Architecture**

```bash
@ngrx-specialist Create comprehensive state management:

Content State Management:
libs/shared/data-access/src/lib/state/content/
├── content.actions.ts
├── content.effects.ts
├── content.reducer.ts
├── content.selectors.ts
├── content.facade.ts
└── index.ts

// Content actions
export const ContentActions = createActionGroup({
  source: 'Content',
  events: {
    // Loading actions
    'Load Content': props<{ contentType: string; options?: ContentQueryOptions }>(),
    'Load Content Success': props<{ contentType: string; content: PaginatedResponse<any> }>(),
    'Load Content Failure': props<{ error: string }>(),

    // CRUD actions
    'Create Content': props<{ contentType: string; data: any }>(),
    'Create Content Success': props<{ contentType: string; content: any }>(),
    'Create Content Failure': props<{ error: string }>(),

    'Update Content': props<{ contentType: string; id: string; data: any }>(),
    'Update Content Success': props<{ contentType: string; content: any }>(),
    'Update Content Failure': props<{ error: string }>(),

    // UI actions
    'Set Selected Content': props<{ contentType: string; id: string }>(),
    'Clear Selected Content': emptyProps(),
    'Set Content Filter': props<{ contentType: string; filters: any }>(),
    'Clear Content Cache': props<{ contentType?: string }>(),
  }
});

// Content effects with advanced error handling
@Injectable()
export class ContentEffects {

  loadContent$ = createEffect(() =>
    this.actions$.pipe(
      ofType(ContentActions.loadContent),
      switchMap(action =>
        this.contentService.getContent(action.contentType, action.options).pipe(
          map(content => ContentActions.loadContentSuccess({
            contentType: action.contentType,
            content
          })),
          catchError(error => {
            this.notificationService.showError(
              `Failed to load ${action.contentType}: ${error.message}`
            );
            return of(ContentActions.loadContentFailure({ error: error.message }));
          })
        )
      )
    )
  );

  createContent$ = createEffect(() =>
    this.actions$.pipe(
      ofType(ContentActions.createContent),
      switchMap(action =>
        this.contentService.createContent(action.contentType, action.data).pipe(
          map(content => {
            this.notificationService.showSuccess(
              `${action.contentType} created successfully`
            );
            return ContentActions.createContentSuccess({
              contentType: action.contentType,
              content
            });
          }),
          catchError(error => {
            this.notificationService.showError(
              `Failed to create ${action.contentType}: ${error.message}`
            );
            return of(ContentActions.createContentFailure({ error: error.message }));
          })
        )
      )
    )
  );

  constructor(
    private actions$: Actions,
    private contentService: ContentService,
    private notificationService: NotificationService
  ) {}
}

// Content selectors with memoization
export const selectContentState = createFeatureSelector<ContentState>('content');

export const selectContentByType = createSelector(
  selectContentState,
  (state: ContentState, props: { contentType: string }) =>
    state.entities[props.contentType] || []
);

export const selectContentLoading = createSelector(
  selectContentState,
  (state: ContentState) => state.loading
);

export const selectContentError = createSelector(
  selectContentState,
  (state: ContentState) => state.error
);

export const selectSelectedContent = createSelector(
  selectContentState,
  (state: ContentState, props: { contentType: string }) => {
    const selectedId = state.selectedIds[props.contentType];
    const entities = state.entities[props.contentType] || [];
    return entities.find(entity => entity.id === selectedId);
  }
);

// Content facade for simplified component interaction
@Injectable({ providedIn: 'root' })
export class ContentFacade {

  // Selectors
  loading$ = this.store.select(selectContentLoading);
  error$ = this.store.select(selectContentError);

  constructor(private store: Store) {}

  getContent(contentType: string, options?: ContentQueryOptions) {
    this.store.dispatch(ContentActions.loadContent({ contentType, options }));
    return this.store.select(selectContentByType, { contentType });
  }

  getContentById(contentType: string, id: string) {
    this.store.dispatch(ContentActions.setSelectedContent({ contentType, id }));
    return this.store.select(selectSelectedContent, { contentType });
  }

  createContent(contentType: string, data: any) {
    this.store.dispatch(ContentActions.createContent({ contentType, data }));
  }

  updateContent(contentType: string, id: string, data: any) {
    this.store.dispatch(ContentActions.updateContent({ contentType, id, data }));
  }

  setFilter(contentType: string, filters: any) {
    this.store.dispatch(ContentActions.setContentFilter({ contentType, filters }));
  }

  clearCache(contentType?: string) {
    this.store.dispatch(ContentActions.clearContentCache({ contentType }));
  }
}
```

#### **Phase 4: Application-Specific Development (Weeks 17-22)**

##### **Admin Portal Application**

```bash
@angular-specialist Develop comprehensive CMS admin portal:

Admin Portal Features:
apps/admin-portal/
├── src/
│   ├── app/
│   │   ├── features/             # Feature modules
│   │   │   ├── content-management/
│   │   │   │   ├── article-editor/
│   │   │   │   ├── page-builder/
│   │   │   │   ├── media-library/
│   │   │   │   └── content-workflow/
│   │   │   ├── user-management/
│   │   │   │   ├── user-list/
│   │   │   │   ├── role-management/
│   │   │   │   └── permissions/
│   │   │   ├── analytics/
│   │   │   │   ├── content-performance/
│   │   │   │   ├── user-analytics/
│   │   │   │   └── site-statistics/
│   │   │   └── settings/
│   │   │       ├── site-config/
│   │   │       ├── api-config/
│   │   │       └── theme-settings/
│   │   ├── shared/               # App-specific shared code
│   │   │   ├── components/
│   │   │   ├── services/
│   │   │   └── guards/
│   │   ├── core/                 # Core app functionality
│   │   │   ├── layout/
│   │   │   ├── auth/
│   │   │   └── navigation/
│   │   └── app.component.ts
│   ├── assets/
│   └── environments/

// Advanced content editor component
@Component({
  selector: 'app-content-editor',
  template: `
    <div class="content-editor" [class.loading]="loading$ | async">

      <!-- Editor toolbar -->
      <mat-toolbar class="editor-toolbar">
        <span>{{ contentType | titlecase }} Editor</span>
        <span class="spacer"></span>

        <button
          mat-button
          [disabled]="!canPreview"
          (click)="preview()">
          <mat-icon>visibility</mat-icon>
          Preview
        </button>

        <button
          mat-button
          [disabled]="!canSave"
          (click)="saveDraft()">
          <mat-icon>save</mat-icon>
          Save Draft
        </button>

        <button
          mat-raised-button
          color="primary"
          [disabled]="!canPublish"
          (click)="publish()">
          <mat-icon>publish</mat-icon>
          Publish
        </button>
      </mat-toolbar>

      <!-- Content form -->
      <div class="editor-content">
        <app-dynamic-form
          [formConfig]="formConfig"
          [initialData]="initialData"
          (formSubmit)="onFormSubmit($event)"
          (formChange)="onFormChange($event)">
        </app-dynamic-form>
      </div>

      <!-- Preview panel -->
      <mat-sidenav-container class="preview-container" *ngIf="showPreview">
        <mat-sidenav
          #previewSidenav
          mode="side"
          opened="true"
          position="end"
          class="preview-panel">

          <div class="preview-header">
            <h3>Live Preview</h3>
            <button
              mat-icon-button
              (click)="closePreview()">
              <mat-icon>close</mat-icon>
            </button>
          </div>

          <div class="preview-content">
            <iframe
              [src]="previewUrl | safe"
              class="preview-iframe">
            </iframe>
          </div>

        </mat-sidenav>
      </mat-sidenav-container>

    </div>
  `,
  styleUrls: ['./content-editor.component.scss'],
  changeDetection: ChangeDetectionStrategy.OnPush,
})
export class ContentEditorComponent implements OnInit, OnDestroy {
  @Input() contentType!: string;
  @Input() contentId?: string;

  loading$ = this.contentFacade.loading$;
  error$ = this.contentFacade.error$;

  formConfig!: FormConfig;
  initialData: any;
  showPreview = false;
  previewUrl: SafeUrl | null = null;

  private destroy$ = new Subject<void>();
  private autoSaveSubscription?: Subscription;

  constructor(
    private contentFacade: ContentFacade,
    private previewService: PreviewService,
    private notificationService: NotificationService,
    private sanitizer: DomSanitizer,
    private cdr: ChangeDetectorRef
  ) {}

  ngOnInit() {
    this.loadFormConfig();
    this.loadContent();
    this.setupAutoSave();
  }

  ngOnDestroy() {
    this.destroy$.next();
    this.destroy$.complete();
    this.autoSaveSubscription?.unsubscribe();
  }

  get canPreview(): boolean {
    return this.initialData && Object.keys(this.initialData).length > 0;
  }

  get canSave(): boolean {
    return this.initialData && this.hasChanges();
  }

  get canPublish(): boolean {
    return this.canSave && this.isValid();
  }

  private loadFormConfig() {
    // Load form configuration based on content type
    this.contentConfigService.getFormConfig(this.contentType)
      .pipe(takeUntil(this.destroy$))
      .subscribe(config => {
        this.formConfig = config;
        this.cdr.markForCheck();
      });
  }

  private loadContent() {
    if (this.contentId) {
      this.contentFacade.getContentById(this.contentType, this.contentId)
        .pipe(takeUntil(this.destroy$))
        .subscribe(content => {
          this.initialData = content;
          this.cdr.markForCheck();
        });
    }
  }

  private setupAutoSave() {
    // Auto-save every 30 seconds if there are changes
    this.autoSaveSubscription = interval(30000)
      .pipe(
        filter(() => this.canSave),
        tap(() => this.saveDraft(true))
      )
      .subscribe();
  }

  preview() {
    this.previewService.generatePreview(this.contentType, this.getCurrentData())
      .subscribe(previewData => {
        this.previewUrl = this.sanitizer.bypassSecurityTrustResourceUrl(
          previewData.url
        );
        this.showPreview = true;
        this.cdr.markForCheck();
      });
  }

  saveDraft(isAutoSave = false) {
    const data = { ...this.getCurrentData(), status: 'draft' };

    if (this.contentId) {
      this.contentFacade.updateContent(this.contentType, this.contentId, data);
    } else {
      this.contentFacade.createContent(this.contentType, data);
    }

    if (!isAutoSave) {
      this.notificationService.showSuccess('Draft saved successfully');
    }
  }

  publish() {
    const data = { ...this.getCurrentData(), status: 'published' };

    if (this.contentId) {
      this.contentFacade.updateContent(this.contentType, this.contentId, data);
    } else {
      this.contentFacade.createContent(this.contentType, data);
    }

    this.notificationService.showSuccess('Content published successfully');
  }

  onFormSubmit(data: any) {
    this.publish();
  }

  onFormChange(data: any) {
    // Handle form changes for real-time preview updates
    if (this.showPreview) {
      this.updatePreview(data);
    }
  }

  private updatePreview(data: any) {
    // Debounced preview updates
    debounceTime(500);
    this.previewService.updatePreview(this.contentType, data)
      .subscribe(previewData => {
        // Update preview iframe content
      });
  }

  private getCurrentData(): any {
    // Get current form data
    return this.currentFormData;
  }

  private hasChanges(): boolean {
    // Compare current data with initial data
    return !isEqual(this.getCurrentData(), this.initialData);
  }

  private isValid(): boolean {
    // Validate current form data
    return this.formValid;
  }
}
```

##### **Public Website Application**

```bash
@angular-specialist Create high-performance public website:

Public Website Features:
apps/public-website/
├── src/
│   ├── app/
│   │   ├── pages/                # Page components
│   │   │   ├── home/
│   │   │   ├── about/
│   │   │   ├── products/
│   │   │   ├── blog/
│   │   │   └── contact/
│   │   ├── components/           # Reusable components
│   │   │   ├── header/
│   │   │   ├── footer/
│   │   │   ├── hero/
│   │   │   ├── product-grid/
│   │   │   └── blog-list/
│   │   ├── resolvers/            # Route resolvers
│   │   ├── pipes/                # Custom pipes
│   │   └── services/             # App-specific services
│   ├── assets/
│   └── environments/

// High-performance page component with SSR
@Component({
  selector: 'app-blog-page',
  template: `
    <div class="blog-page">

      <!-- SEO meta tags are handled by resolver -->

      <!-- Hero section -->
      <app-hero
        [title]="page.title"
        [subtitle]="page.subtitle"
        [backgroundImage]="page.heroImage">
      </app-hero>

      <!-- Blog content -->
      <div class="container">
        <div class="blog-grid">
          <article
            *ngFor="let article of articles$ | async; trackBy: trackByArticleId"
            class="blog-card"
            [routerLink]="['/blog', article.slug]">

            <div class="card-image">
              <img
                [src]="article.featuredImage?.url"
                [alt]="article.featuredImage?.alt"
                [attr.loading]="'lazy'"
                [attr.width]="article.featuredImage?.width"
                [attr.height]="article.featuredImage?.height">
            </div>

            <div class="card-content">
              <h2>{{ article.title }}</h2>
              <p class="excerpt">{{ article.excerpt }}</p>

              <div class="meta">
                <span class="author">{{ article.author.name }}</span>
                <span class="date">{{ article.publishedAt | date }}</span>
                <span class="read-time">{{ article.readTime }} min read</span>
              </div>

              <div class="tags">
                <span
                  *ngFor="let tag of article.tags"
                  class="tag">
                  {{ tag.name }}
                </span>
              </div>
            </div>

          </article>
        </div>

        <!-- Pagination -->
        <app-pagination
          [currentPage]="currentPage"
          [totalPages]="totalPages"
          [totalItems]="totalItems"
          (pageChange)="onPageChange($event)">
        </app-pagination>

      </div>

    </div>
  `,
  styleUrls: ['./blog-page.component.scss'],
  changeDetection: ChangeDetectionStrategy.OnPush,
})
export class BlogPageComponent implements OnInit {

  articles$: Observable<Article[]>;
  currentPage = 1;
  totalPages = 0;
  totalItems = 0;

  page: any; // Resolved page data

  constructor(
    private contentFacade: ContentFacade,
    private route: ActivatedRoute,
    private seoService: SeoService,
    private cdr: ChangeDetectorRef
  ) {
    this.page = this.route.snapshot.data['page'];
  }

  ngOnInit() {
    this.loadArticles();
    this.setupSEO();
  }

  private loadArticles() {
    this.articles$ = this.contentFacade.getContent('articles', {
      sort: { field: 'publishedAt', direction: 'DESC' },
      page: this.currentPage,
      limit: 12,
      include: ['author', 'tags', 'featuredImage']
    }).pipe(
      tap(response => {
        this.totalPages = response.meta.totalPages;
        this.totalItems = response.meta.totalItems;
        this.cdr.markForCheck();
      })
    );
  }

  private setupSEO() {
    this.seoService.updateTags({
      title: this.page.seoTitle || this.page.title,
      description: this.page.seoDescription,
      keywords: this.page.seoKeywords,
      ogTitle: this.page.ogTitle,
      ogDescription: this.page.ogDescription,
      ogImage: this.page.ogImage?.url,
      canonicalUrl: this.page.canonicalUrl,
    });
  }

  onPageChange(page: number) {
    this.currentPage = page;
    this.loadArticles();

    // Update URL without reloading page
    this.router.navigate([], {
      relativeTo: this.route,
      queryParams: { page: page > 1 ? page : null },
      queryParamsHandling: 'merge'
    });
  }

  trackByArticleId(index: number, article: Article): string {
    return article.id;
  }
}

// Page resolver for SSR and SEO
@Injectable({ providedIn: 'root' })
export class PageResolver implements Resolve<any> {

  constructor(
    private contentService: ContentService,
    private seoService: SeoService
  ) {}

  resolve(route: ActivatedRouteSnapshot): Observable<any> {
    const pageSlug = route.params['slug'] || 'home';

    return this.contentService.getContent('pages', {
      filters: { slug: pageSlug },
      include: ['seoData', 'heroImage']
    }).pipe(
      map(response => response.data[0]),
      tap(page => {
        if (page) {
          // Pre-configure SEO data for SSR
          this.seoService.preloadSEOData(page.seoData);
        }
      }),
      catchError(() => {
        // Return 404 page data if page not found
        return this.contentService.getContent('pages', {
          filters: { slug: '404' }
        }).pipe(
          map(response => response.data[0])
        );
      })
    );
  }
}
```

#### **Phase 5: Performance & SEO Optimization (Weeks 23-26)**

##### **Angular Universal SSR Setup**

```bash
@performance-specialist Implement comprehensive SSR and performance optimization:

Angular Universal Configuration:
# Add Angular Universal
ng add @nguniversal/express-engine

# Configure for optimal SSR performance
// server.ts
import { ngExpressEngine } from '@nguniversal/express-engine';
import { APP_BASE_HREF } from '@angular/common';
import express from 'express';
import { existsSync } from 'fs';

import { AppServerModule } from './src/main.server';

const app = express();
const PORT = process.env['PORT'] || 4000;
const DIST_FOLDER = join(process.cwd(), 'dist');

// Configure Express engine
app.engine('html', ngExpressEngine({
  bootstrap: AppServerModule,
  inlineCriticalCss: true,
  enablePerformanceProfiler: false,
}));

app.set('view engine', 'html');
app.set('views', DIST_FOLDER);

// Serve static files with proper caching
app.get('*.*', express.static(DIST_FOLDER, {
  maxAge: '1y',
  etag: true,
  setHeaders: (res, path) => {
    if (path.includes('index.html')) {
      res.setHeader('Cache-Control', 'no-cache');
    }
  }
}));

// Server-side rendering with caching
const cache = new Map();
const CACHE_TTL = 5 * 60 * 1000; // 5 minutes

app.get('*', (req, res) => {
  const cacheKey = req.url;
  const cached = cache.get(cacheKey);

  if (cached && Date.now() - cached.timestamp < CACHE_TTL) {
    return res.send(cached.html);
  }

  res.render('index', { req }, (err, html) => {
    if (err) {
      console.error('SSR Error:', err);
      res.status(500).send('Server Error');
      return;
    }

    // Cache successful renders
    cache.set(cacheKey, {
      html,
      timestamp: Date.now()
    });

    res.send(html);
  });
});

app.listen(PORT, () => {
  console.log(`Node Express server listening on http://localhost:${PORT}`);
});

Service Worker Configuration:
// ngsw-config.json
{
  "index": "/index.html",
  "assetGroups": [
    {
      "name": "app",
      "installMode": "prefetch",
      "resources": {
        "files": [
          "/favicon.ico",
          "/index.html",
          "/manifest.webmanifest",
          "/*.css",
          "/*.js"
        ]
      }
    },
    {
      "name": "assets",
      "installMode": "lazy",
      "updateMode": "prefetch",
      "resources": {
        "files": [
          "/assets/**",
          "/*.(eot|svg|cur|jpg|png|webp|gif|otf|ttf|woff|woff2|ani)"
        ]
      }
    }
  ],
  "dataGroups": [
    {
      "name": "api-content",
      "urls": [
        "/api/v1/content/**"
      ],
      "cacheConfig": {
        "maxSize": 100,
        "maxAge": "1h",
        "timeout": "10s",
        "strategy": "freshness"
      }
    },
    {
      "name": "api-media",
      "urls": [
        "/api/v1/media/**"
      ],
      "cacheConfig": {
        "maxSize": 50,
        "maxAge": "1d",
        "strategy": "performance"
      }
    }
  ]
}

Performance Optimization Service:
@Injectable({ providedIn: 'root' })
export class PerformanceService {
  private performanceObserver?: PerformanceObserver;

  constructor() {
    this.initializePerformanceMonitoring();
  }

  private initializePerformanceMonitoring() {
    if (typeof window !== 'undefined' && 'PerformanceObserver' in window) {
      // Monitor Core Web Vitals
      this.observeWebVitals();

      // Monitor resource loading
      this.observeResourceTiming();

      // Monitor navigation timing
      this.observeNavigationTiming();
    }
  }

  private observeWebVitals() {
    // Largest Contentful Paint
    new PerformanceObserver((list) => {
      for (const entry of list.getEntries()) {
        console.log('LCP:', entry.startTime);
        this.reportMetric('lcp', entry.startTime);
      }
    }).observe({ entryTypes: ['largest-contentful-paint'] });

    // First Input Delay
    new PerformanceObserver((list) => {
      for (const entry of list.getEntries()) {
        const fid = entry.processingStart - entry.startTime;
        console.log('FID:', fid);
        this.reportMetric('fid', fid);
      }
    }).observe({ entryTypes: ['first-input'] });

    // Cumulative Layout Shift
    let cumulativeLayoutShift = 0;
    new PerformanceObserver((list) => {
      for (const entry of list.getEntries()) {
        if (!entry.hadRecentInput) {
          cumulativeLayoutShift += entry.value;
        }
      }
      console.log('CLS:', cumulativeLayoutShift);
      this.reportMetric('cls', cumulativeLayoutShift);
    }).observe({ entryTypes: ['layout-shift'] });
  }

  private reportMetric(metric: string, value: number) {
    // Send metrics to analytics service
    if (environment.production) {
      // Send to Google Analytics, custom analytics, etc.
      gtag('event', 'performance_metric', {
        metric_name: metric,
        metric_value: Math.round(value),
        custom_parameter: true
      });
    }
  }

  preloadCriticalResources() {
    // Preload critical fonts
    this.preloadResource('/assets/fonts/main.woff2', 'font', 'font/woff2');

    // Preload hero images
    this.preloadResource('/assets/images/hero.webp', 'image');

    // Prefetch next page resources
    this.prefetchRoute('/about');
  }

  private preloadResource(href: string, as: string, type?: string) {
    const link = document.createElement('link');
    link.rel = 'preload';
    link.href = href;
    link.as = as;
    if (type) link.type = type;
    link.crossOrigin = 'anonymous';
    document.head.appendChild(link);
  }

  private prefetchRoute(route: string) {
    const link = document.createElement('link');
    link.rel = 'prefetch';
    link.href = route;
    document.head.appendChild(link);
  }
}
```

---

## 🎯 **Deployment & DevOps Integration (Weeks 27-28)**

##### **Comprehensive CI/CD Pipeline**

```bash
@devops-specialist Setup enterprise-grade CI/CD pipeline:

GitHub Actions Workflow:
# .github/workflows/ci-cd.yml
name: CI/CD Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

env:
  NX_CLOUD_ACCESS_TOKEN: ${{ secrets.NX_CLOUD_ACCESS_TOKEN }}

jobs:
  setup:
    runs-on: ubuntu-latest
    outputs:
      affected-apps: ${{ steps.affected.outputs.apps }}
      affected-libs: ${{ steps.affected.outputs.libs }}
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Determine affected projects
        id: affected
        run: |
          echo "apps=$(npx nx show projects --affected --type=app --json)" >> $GITHUB_OUTPUT
          echo "libs=$(npx nx show projects --affected --type=lib --json)" >> $GITHUB_OUTPUT

  lint-and-test:
    needs: setup
    runs-on: ubuntu-latest
    strategy:
      matrix:
        project: ${{ fromJson(needs.setup.outputs.affected-apps) }}
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Lint
        run: npx nx lint ${{ matrix.project }}

      - name: Test
        run: npx nx test ${{ matrix.project }} --coverage

      - name: Upload coverage
        uses: codecov/codecov-action@v3
        with:
          file: ./coverage/${{ matrix.project }}/lcov.info

  build-and-deploy:
    needs: [setup, lint-and-test]
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    strategy:
      matrix:
        app: ${{ fromJson(needs.setup.outputs.affected-apps) }}
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Build application
        run: npx nx build ${{ matrix.app }} --prod

      - name: Build Docker image
        run: |
          docker build -t ${{ matrix.app }}:${{ github.sha }} \
            -f apps/${{ matrix.app }}/Dockerfile .

      - name: Deploy to staging
        if: github.ref == 'refs/heads/develop'
        run: |
          # Deploy to staging environment
          echo "Deploying ${{ matrix.app }} to staging"

      - name: Deploy to production
        if: github.ref == 'refs/heads/main'
        run: |
          # Deploy to production environment
          echo "Deploying ${{ matrix.app }} to production"

Docker Configuration:
# Dockerfile for Angular Universal app
FROM node:18-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npx nx build app-name --prod
RUN npx nx build app-name --prod --app=server

FROM node:18-alpine AS runtime

WORKDIR /app

# Copy built application
COPY --from=builder /app/dist ./dist
COPY package*.json ./
RUN npm ci --only=production

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:4000/health || exit 1

EXPOSE 4000

CMD ["node", "dist/server/main.js"]

Kubernetes Deployment:
# k8s/deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: angular-app
  labels:
    app: angular-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: angular-app
  template:
    metadata:
      labels:
        app: angular-app
    spec:
      containers:
      - name: angular-app
        image: angular-app:latest
        ports:
        - containerPort: 4000
        env:
        - name: NODE_ENV
          value: "production"
        - name: API_URL
          valueFrom:
            configMapKeyRef:
              name: app-config
              key: api-url
        resources:
          requests:
            memory: "256Mi"
            cpu: "100m"
          limits:
            memory: "512Mi"
            cpu: "500m"
        livenessProbe:
          httpGet:
            path: /health
            port: 4000
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /ready
            port: 4000
          initialDelaySeconds: 5
          periodSeconds: 5
```

---

## 🏆 **Success Metrics & KPIs**

### **Technical Performance Metrics**

#### **Frontend Performance**

- **Core Web Vitals**: LCP < 2.5s, FID < 100ms, CLS < 0.1
- **Bundle Size**: Initial bundle < 250KB gzipped
- **Lighthouse Scores**: Performance > 90, SEO > 95, Accessibility > 95
- **Time to Interactive**: < 3 seconds on 3G networks

#### **Development Velocity**

- **Build Time**: Full monorepo build < 10 minutes
- **Hot Reload**: < 2 seconds for development changes
- **Test Execution**: Full test suite < 15 minutes
- **Deployment Time**: < 5 minutes per application

#### **Code Quality Metrics**

- **Test Coverage**: > 85% for critical paths
- **TypeScript Strict Mode**: 100% compliance
- **ESLint Violations**: Zero errors, < 5 warnings
- **Bundle Analysis**: No duplicate dependencies

### **Business Impact Metrics**

#### **Content Management Efficiency**

- **Content Publishing Time**: < 2 minutes from draft to live
- **Editor Productivity**: 50% reduction in content creation time
- **Content Updates**: Real-time preview and publishing
- **Multi-language Support**: < 1 minute to add translations

#### **SEO & Discoverability**

- **SEO Score**: > 95 Lighthouse SEO score
- **Meta Tag Automation**: 100% automated meta tag generation
- **Structured Data**: Complete schema.org implementation
- **Sitemap Generation**: Automated XML sitemap updates

#### **User Experience**

- **Page Load Speed**: < 2 seconds perceived load time
- **Accessibility Compliance**: WCAG 2.1 AA compliance
- **Mobile Performance**: 90+ mobile Lighthouse score
- **Offline Functionality**: Core content available offline

---

## 🚀 **Agent Genesis Advantages for Angular NX + Headless CMS**

### **Intelligent Coordination**

- **Multi-team synchronization** across backend and frontend teams
- **Dependency conflict resolution** in complex monorepo structures
- **Performance optimization** across all applications
- **Real-time quality monitoring** and automated corrections

### **Scalable Architecture**

- **Micro-frontend ready** architecture with NX workspace
- **API-first design** with headless CMS integration
- **Component-driven development** with shared libraries
- **Enterprise-grade** security and performance patterns

### **Automated Excellence**

- **Code generation** for consistent patterns
- **Testing automation** across the entire stack
- **Performance monitoring** with automated optimization
- **SEO automation** with structured data generation

### **Future-Proof Technology**

- **Modern Angular patterns** with standalone components
- **Advanced state management** with NgRx
- **Progressive Web App** capabilities out of the box
- **Server-side rendering** for optimal performance and SEO

**Transform your enterprise Angular development with intelligent agent coordination and proven architectural patterns!** 🏗️✨
